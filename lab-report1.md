#Lab Report 1
Elaine Chao
A16894921
4/10/2022

## Installing VS Code
I already had VS Code installed. 

However, if I hadn't, I would have had to install it from the [VS Code Website](https://code.visualstudio.com).
![VS code screenshot](https://user-images.githubusercontent.com/34292064/162668878-b45949ab-15bd-46bd-bfee-8d6847bf5d1a.png)
*A screenshot of what VS Code looks like opened.*

## Remotely Connecting
![image](https://user-images.githubusercontent.com/34292064/162669454-9aa178d0-c0af-4320-9046-19842e40dd39.png)


## Trying Some Commands
![image](https://user-images.githubusercontent.com/34292064/162669580-ba5f0836-6984-4f21-b395-2788b4522a49.png)


## Moving Files with scp
![image](https://user-images.githubusercontent.com/34292064/162669630-e71ed40a-3846-451b-bade-771ceff9beb4.png)


## Setting an SSH Key
To be able to log in without a password, we can generate ssh keys that can be used instead of a password. To generate the keys, I ran ssh-keygen on my local computer and did not set a password. This will generate the key pair.


Since I'm on Windows, I then have to make sure that OpenSSH is installed.
![image](https://user-images.githubusercontent.com/34292064/162670025-5c5a8372-8bdd-41c2-a9bf-c46912aa474f.png)
And then I ran ssh-add as administrator to store my private key.
```
Get-Service ssh-agent | Set-Service -StartupType Manual
Start-Service ssh-agent
ssh-add ~\.ssh\id_ed25519
```
[Source](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)


Next, on the server I ran mkdir .ssh
On the client, I ran scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys

![image](https://user-images.githubusercontent.com/34292064/162669739-13f1fdec-5b21-4f7b-92bb-6458de10ba42.png)
*Now, I can connect remotely without having to sign in.*

## Optimizing Remote Running
![image](https://user-images.githubusercontent.com/34292064/162669806-8d445b3f-4c28-4dec-9d3b-85375383e400.png)
*I was able to run the command in the same line as the ssh command, without logging in.*
