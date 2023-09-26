# Creating SSH Keys

## GitBash

### Getting Started

- `pwd` - Shows current folder
- Navigate to main folder `/c/Users/(profile_name)`
- `ls` - shows folders within current directory
- `ls -a` - shows hidden folders and files within directory that begin with . (e.g. .ssh).

#### If SSH folder doesn't exist (should only need to be done once):

- `mkdir .ssh` - Makes a directory (.ssh is name given to directory).

### Making an SSH key


- Type `ssh-keygen -t rsa -b 4096 -C your.email@here.comgit`
- `-t rsa`  is the type of encryption (with rsa being the type chosen).
- `-b 4096` is for the number of bits in the key (4096 the chosen standard).
- `-C <your. email@here.com` is the comment you add at the end of the key (makes easier to see where the key ends).
- Assign a descriptive name to the key (e.g. github_ssh).
- You can add a passphrase but its not necessary.
- Using `ls` in the terminal will show the private and public keys you made (e.g. `keyname` and `keyname.pub`)

### Setting up Public key on GitHub

- Go to your GitHub profile.
- Click on top right icon (which usually takes you to your profile page).
- Click on `settings`
- Navigate to the `SSH and GPG keys` section on the left hand side of the page.
![sh.1.jpg](..%2F..%2F..%2F..%2FOneDrive%20-%20Sparta%20Global%2FPictures%2FSSH%2Fsh.1.jpg)
- Click on `New SSH key` in the SSH keys (make sure there isn't one there already).
- Give the key a descriptive name.
- Return to the GitBash terminal you are using. This is where the Public key needs to be copied from the .ssh directory to be added to GitBash.
- Input `cat <keyname.pub>`
- **Make sure only the PUBLIC key is copied!**
- Copy the output generated above **(Make sure there is no WHITESPACE at the end)**.
- Paste it into GitHub.
- Public SSH key should now be linked to GitHub.
![sh.2.jpg](..%2F..%2F..%2F..%2FOneDrive%20-%20Sparta%20Global%2FPictures%2FSSH%2Fsh.2.jpg)

### Creating an SSH agent

- Type `eval ssh_agent` into the terminal.
- This creates an agent with a PID value.

### Connecting the Private key

- Type `ssh-add ~/.ssh/keyname` into the terminal
- Test the connection with `ssh -T git@github.com` (the -T means test)
- Create a new repository on GitHub to link to Git via the SSH key.
- Copy `git remote add origin git@github.com:repo_name_here.git` into the GitBash terminal.
- Navigate the terminal to the folder being linked to GitHub.
- Do a `git init` as normal.
- Link the repos using `git remote set-url origin git@github.com:repo_name_here.git`

### TROUBLESHOOTING

#### Permission Denied: Could not read from remote repository.


