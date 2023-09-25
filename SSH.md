# **SSH**

## **What is SSH?**

- SSH - Secure Shell.
- It is a network communication protocol that enables two computers to communicate and share data.
- The communication is encrypted so it is suitable for use on unsecure networks.

## **What is SSH used for?**

- Secure Shell is used to connect to servers, make changes, perform uploads and exit, either using tools or directly through the terminal. SSH keys can be employed to automate access to servers and often are used in scripts, backup systems and configuration management tools.

## **How does SSH work?**

- The most basic use of SSH is to connect to a remote host for a terminal session. The form of that command is the following:

`ssh UserName@SSHserver.example.com`
- This command will cause the client to attempt to connect to the server named server.example.com, using the user ID UserName. If this is the first time negotiating a connection between the local host and the server, the user will be prompted with the remote host's public key fingerprint and prompted to connect, despite there having been no prior connection:

````
The authenticity of host 'sample.ssh.com' cannot be established.
 
 DSA key fingerprint is 01:23:45:67:89:ab:cd:ef:ff:fe:dc:ba:98:76:54:32:10.
 Are you sure you want to continue connecting (yes/no)?
 ````
 
- Answering yes to the prompt will cause the session to continue, and the host key is stored in the local system's known_hosts file. This is a hidden file, stored by default in a hidden directory, called /.ssh/known_hosts, in the user's home directory. Once the host key has been stored in the known_hosts file, the client system can connect directly to that server again without need for any approvals; the host key authenticates the connection.

## **Why is SSH secure?**

- Uses encryption technologies.

The SSH key pair is used to authenticate the identity of a user or process that wants to access a remote system using the SSH protocol. The public key is used by both the user and the remote server to encrypt messages. On the remote server side, it is saved in a public key file. On the user’s side, it is stored in SSH key management software or in a file on their computer. The private key remains only on the system being used to access the remote server and is used to decrypt messages.