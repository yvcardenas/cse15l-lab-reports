# Lab Report 1 - Remote Access and FileSystem (Week 1)
In each of the following examples we will be going over the commands **cd** "change directory", **ls** "list files", and **cat** "concatenate".
## Examples using the commands with no arguments
![Image](LR1ex1.png) <br>
*All of these examples were done in the home directory*
### cd 
This commands whole purpose is to change the directory you are in. This example is an not error because although no argument is given it kept us in the home directory. It usually is accompanied with a path, but in the case the case where one is not provided, it simply changes to the home directory.  
### ls
This command lists or 'prints' the files and/or folder in the given path. This example is not an error. Since no path is given, it printed the files and folder within the current directory we were in. In this case we were in the home directory so it only printed 'lecture1' since that is the only folder in that directory.
### cat
This commands purpose is to print the contents of one or more files given by the provided path. This is an error because no path or argument was given, and it simply does not let you run it. Ultimately it is waiting for the user to input a path, but since we did not have one we used '^C' to exit.
## Examples using the commands with a path to a directory as an argument
![Image](LR1ex2.png) <br>
*The first example was done in the home directory, and the last two were done in the messages directory*
### cd
This example is not an error. Now that the command has been given a path to follow, it can change to a specific  directory. The path given was '/home/lecture1/messages' so it should and did change to the messages directory. 
### ls
This example is not an error. Now that the command has been given a path to follow, it can list all the files and/or folders in that specific folder. Since the path that I provided led to the  working directory messages, it listed all the files/folders in the the messages directory. 
### cat
As I mentioned earlier, the cat command prints the contents of one or more files. Since the path provided led to a directory/folder the command was unable to properly function. This example is an error. Instead of printing a files content, it informed the user that the argument was indeed a directory.
## Examples using the commands with a path to a file as an argument
![Image](LR1ex3.png) <br>
*All of these examples were done in the home directory*
### cd
As we know, the cd command is used to change directories. In this example the given path led to a file which evidently meant that command was unable to properly frunction. This example is an error. Instead a message was printed informing the user that the path given was not to a directory. 
### ls
As we saw in the last set of examples, a path can be used as an argument when using the ls command. A very important difference is that this path led to a file, so the command was unable to properly function. This example is an error. No content was printed because a file connot hold any files and/or folders. In respose to this path, the command simply printed the path again.
### cat
In this example we get to finally see a functioning cat command. This example is not an error. Since the path given was to a file, its content was printed. In this case the path leads to a file named 'es-mx.txt' and prints its content which is '¡Hola Mundo!' which means 'Hello World!' in Mexican Spanish.
