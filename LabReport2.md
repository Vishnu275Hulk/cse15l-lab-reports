# Lab Report 2

This lab report will be showing how a web server is created and demonstrate a few operations on the web server. It will also focus on how a bug in a code must be dealt with systematically. 

# Part 1: Servers
  * Following is the code for StringServer.java. This is a program with a main method that creates a URLHandler that keeps track of a single string that gets added to by incoming request, and uses Server.java to start a web server using that handler. It makes use of the `URLHandler` interface which builds URLs for links to content pages. The Handler class takes a URLHandler and starts up the server that listens for incoming connections.

![Image](ss1_lab2.png)

  * The execution of StringServer.java is shown in the image below. The code is called using `javac StringServer.java Server.java` and then `java StringServer 7049`. **7049** is a port number. It doesn't have to be 7049, it can be any number between 1024 and 49151.

![Image](ss2_lab2.png)

  * Here is an example of how the code is implemeneted on the web.

![Image](ss4_lab2.png)

The main method in the StringServer class is called first. It checks if the argument is empty or not. Since it is not empty but has **7049** as the argument, it stores **7049** in the port field. It then generates a url.
When we enter this url on the web, the `handleRequest(URI url)` method is called. First, it checks if the path equals `/add-message` and the query starts with `s`. Then, it stores the "Hello" string in the message field and adds it to request. Finally, we print the desired string on the webpage. 

 * Here is another example. This time the code does a little more to give us a result.

![Image](ss3_lab2.png)

The process is exactly the same in printing "I". The code, however, does a little more in the end to obtain more strings. When we enter the string "I want the truth!", this string gets stored in the message field and is added to the request field on a new line. When we print request we get both "I" and "I want the truth!" together but on different lines because they are stored in the request field. Likewise, as we type in more strings in the url, the strings are successively added to the request field and get printed together. The request field simply keeps track of the strings that iterated through the `handleRequest(URI url)` method.
