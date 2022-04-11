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
I found my course specific account at [https://sdacs.ucsd.edu/~icc/index.php](https://sdacs.ucsd.edu/~icc/index.php).

In terminal, I ran ssh cs15lsp22zz@ieng6.ucsd.edu with zz being my account id. When it asked "Are you sure you want to continue connecting?" I typed in yes.
![image](https://user-images.githubusercontent.com/34292064/162669454-9aa178d0-c0af-4320-9046-19842e40dd39.png)

*Remotely connected to the server.*

## Trying Some Commands
Next, I ran some commands on the server. I tried ls, which worked, and ls /home/linux/ieng6/cs15lsp22/cs15lsp22abc (with the cs15lsp22 account being my groupmate's) which did not work.
![image](https://user-images.githubusercontent.com/34292064/162669580-ba5f0836-6984-4f21-b395-2788b4522a49.png)

## Moving Files with scp
I created a local file called WhereAmI.java that contained this code.
```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```

Running it in terminal using javac and java, I got an output of my user and operating system of the computer I was on. Next, still in the local directory, I ran scp WhereAmI.java cs15lsp22zz@ieng6.ucsd.edu:~/ and entered the password when it asked.

Afterwards, I logged into the remote server again and, using ls, found the WhereAmI.java file there. I ran it on the remote server and it gave me the ieng6 details.

![image](https://user-images.githubusercontent.com/34292064/162669630-e71ed40a-3846-451b-bade-771ceff9beb4.png)


## Setting an SSH Key
To be able to log in without a password, we used ssh keys. To generate the keys, I ran ssh-keygen on my local computer and did not set a password. This will generate the key pair.


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
There are two additional things to do to optimize remote running:
  * run the command in quotes right after the ssh command
  * run multiple commands by separating them with a semicolon

![image](https://user-images.githubusercontent.com/34292064/162669806-8d445b3f-4c28-4dec-9d3b-85375383e400.png)
 
*Here, I was able to run the command in the same line as the ssh command, without logging in.*
