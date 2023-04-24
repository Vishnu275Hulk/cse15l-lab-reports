# Lab Report 2

This lab report will be showing how a web server is created and demonstrate a few operations on the web server. It will also focus on how a bug in a code must be dealt with systematically. 

# Part 1: Servers
  * Following is the code for StringServer.java. This is a program with a main method that creates a URLHandler that keeps track of a single string that gets added to by incoming request, and uses Server.java to start a web server using that handler. It makes use of the `URLHandler` interface which builds URLs for links to content pages. The Handler class takes a URLHandler and starts up the server that listens for incoming connections.

![Image](ss1_Lab2.png)

  * The execution of StringServer.java is shown in the image below. The code is called using `javac StringServer.java Server.java` and then `java StringServer 7049`. **7049** is a port number. It doesn't have to be 7049, it can be any number between 1024 and 49151.

![Image](ss2_Lab2.png)

  * Here is an example of how the code is implemeneted on the web.

![Image](ss4_Lab2.png)

