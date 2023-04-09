# Lab Report 1

In this blog, I am going to give you a tutorial on how to get remote access through a macOS computer. First of all, what is remote access? It is a feature that enables users to access a device or network from any location. With this access, users can manage files and data that are stored on that remote device. This feature facilitates collaboration from any part of the world. Acquiring remote access for the course CSE 15L involves the following steps:

## 1. Accessing Your Course-Specific Account  
   * In order to access the remote server, you'll need to access your course specific account information for CSE 15L. And to do that you'll need to go to [Account Lookup](https://sdacs.ucsd.edu/~icc/index.php) and enter your details as prompted in the picture below.

![Image](Screenshot1.png)

   * After your account is found, you'll see something similar to the image below. You'll be able to view your CSE 15L username. The username goes *"cs15lsp23xx"* where xx are specific to your username.

![Image](Screenshot2.png)

   * Click on the CSE 15L username and you should see a link where you can change your password as shown below. Click on the link and follow the directions to change your password.

![Image](Screenshot3.png)

***Don't forget to note down your username and password!***

## 2. Installing VS Code
   * Visual Studio Code is a code editor that also provides support for development operations such as debugging, task-running, and version-control. To install VS Code, go to [VSCode](https://code.visualstudio.com/). Then, download the stable version for macOS.

![Image](Screenshot4.png)

   * After expanding the downloaded zip file, you'll be able to start the application. After you start the application, the home page of VS Code should look somewhat similar to the following image.

![Image](Screenshot5.png)

## 3. Acquiring Remote Connection
   * Till now you have been setting up tools you require to attain remote access. This is the step where you will actually be able to gain remote access. Open a terminal on VS Code and enter the command as visible in the image below but be sure to input **your** username in place of "aj".
![Image](Screenshot6.png)

  * If this is the first time you've connected to the remote server, then you'll most likely see something similar to the following message:

```
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```

This is a message to tell you that you've never connected to a remote server before. It is just trying to get confirmation that you want to continue to login to the remote server. Since you'll have an encrypted channel anyway, type "yes" and continue to login with your course-specific account's password.
  * Once you're in the remote server, you'll see something like this:
  
![Image](Screenshot7.png)

This means that you've established a connection with the remote server. Congratulations, you've just gained remote access!

## 4. Try Running Some Commands
  * Now, lets try running a few commands just to see what outputs you'd get on the remote server. Try running `$ ls -lat`. It lists out the contents in your current working directory of the remote shell.

![Image](Screenshot8.png)

  * If you run `$ ls /home/linux/ieng6/cs15lsp23/`, you would see all the usernames in your current CSE 15L class listed out.

![Image](Screenshot9.png)

There you go! You've just ran commands on a remote server!
