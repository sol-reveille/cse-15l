# Lab Report 3

Elaine Chao

A16894921

## Streamlining SSH configuration
First, I edited the ~/.ssh/config file in VS Code to set ieng6 as the server's nickname.

![image](https://user-images.githubusercontent.com/34292064/167538426-ce25ef93-234a-430b-b028-6baa685d13cc.png)

Now, I can call the remote server "ieng6" when ssh-ing into it instead of having to type out cs15lsp22amb@ieng6.ucsd.edu.

![image](https://user-images.githubusercontent.com/34292064/167538469-3f5aa4b2-e854-4afb-b1bf-53f49c00872d.png)

I can also use ieng6 when I'm using scp to move files into the remote server. Here, I scp SkillDemo.java into the remote server.

![image](https://user-images.githubusercontent.com/34292064/167540168-ae8319c6-11f6-4b9c-924a-1354688aa362.png)

## Setup Github access from ieng6
The public SSH key is added to my github account.

![image](https://user-images.githubusercontent.com/34292064/167542504-dbb37b85-e9a9-417b-a7f6-50ff59353e0d.png)

The private key is stored on my ieng6 account in the .ssh folder.

![image](https://user-images.githubusercontent.com/34292064/167542676-2b63f293-fb28-4a90-81a1-8fb7613e3656.png)

I can now commit to my Github repo from my ieng6 account.

![image](https://user-images.githubusercontent.com/34292064/167542589-ce7f476d-6461-4136-935e-8c3098713ebb.png)

Link to the commit: [https://github.com/sol-reveille/markdown-parser/commit/8fa9a1c0e72ec61c6ca870d7294f716b13605a97](https://github.com/sol-reveille/markdown-parser/commit/8fa9a1c0e72ec61c6ca870d7294f716b13605a97)

## Copying whole directories

I used scp -r to copy the entire markdown-parse directory into ieng6.

![image](https://user-images.githubusercontent.com/34292064/167543541-4a8291ea-7fc1-482a-ad39-0d1ef2674ea5.png)

Then, I can log into the remote server and run my markdown-parse tests there.

![image](https://user-images.githubusercontent.com/34292064/167543799-b8793e05-d506-4bd4-874a-4b2eb5fe0afc.png)

I can also combine the scp and ssh commands into one line using a semicolon, as well as the compile and run commands for the tester file.

![image](https://user-images.githubusercontent.com/34292064/167544563-012d8c05-d181-4381-adc4-d8951403fd8b.png)

![image](https://user-images.githubusercontent.com/34292064/167544733-142c518d-1345-4087-ac83-83d4e634c188.png)

