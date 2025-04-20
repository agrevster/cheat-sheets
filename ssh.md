# SSH 101
*This guide will discuss connecting and configuring SSH.*
> "OpenSSH is the premier connectivity tool for remote login with the SSH protocol. It encrypts all traffic to eliminate eavesdropping, connection hijacking, and other attacks. In addition, OpenSSH provides a large suite of secure tunneling capabilities, several authentication methods, and sophisticated configuration options." ~ OpenSSH
----------


## What is SSH?
SSH stands for **S**secure **SH**ell, and is a cryptographic network protocol used to securely access and manage devices over secure and unsecured networks. In English, this means that SSH allows you to securely run commands on devices.


#### So, how does it do this?

SSH has two parts that make secure remote communication possible.

| Service | Job                                                                                                                                                                                                                  |
|---------|---------------------------------------------------------------------------------|
| Client  | Connects you to the SSH server and decrypts traffic from the server, and encrypts what you send to the server.                                                                                                       |
| Server  | Runs on the machine you are trying to connect to. Checks to make sure the client is using proper login, then creates a secure connection allowing the client to run terminal commands, and send files to the server. |



## Connecting to SSH
1. Ensure that there is an SSH server active on the host.
	- If you have physical access to the host and sudo privileges, run `sudo systemctl status sshd`. If the command says the SSH server is running, you are good to go. *(assuming you don’t have SSH blocked by a firewall)*
2. Ensure that your machine has an SSH client. 
	- Go to your terminal and run `which ssh`, if it comes back with a location, you are ready to connect.
3. Now, simply run the SSH command like so...
	- `ssh <USERNAME>@<IP ADDRESS>` 
	- EX: `ssh joe@192.168.0.192`
	- You will be prompted for a password. Enter the account password for the username you are logging in with, and you’re golden!

### Troubleshooting 
In the event that you are not able to connect, use this guide to help diagnose the problem.

| Error | Possible Cause |
|--|--|
| Connection Refused | SSH Server not running<br>SSH Server running on a non standard port *(not 22)*<br>Firewall blocking SSH |
| Connection Timed Out| Server down <br> Network issue<br>Firewall blocking SSH|
|Permission Denied| Wrong username or password **(MOST LIKELY)**<br>SSH key not accepted<br> SSH folder permission misconfiguration|
|"REMOTE HOST IDENTIFICATION HAS CHANGED”|  **BEWARE:** Someone could be listening to your connection... or you just changed the server’s key. Just be careful if you didn’t touch the server and get this message.|
|No route to host| Check your internet connection.|


