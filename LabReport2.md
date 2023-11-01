# Lab Report 2 - Servers and SSH Keys
## Part 1
I have created a web server called StringServer that supports the path and behavior described below. It keeps track of a single string that gets added to by incoming requests that look like "/add-message?s=<String>".
<br>Before any request has been added, the server shows this page which is encouraging the user to input their message!
![Image] ()
### Example 1
After adding the request "/add-message?s=Hello" we get this page:
![Image] ()
- Which methods in your code are called?
- What are the relevent arguments to those methods, and the values of any relevent fields of the class?
- How do the values of any relevent fields of the class change from this specific request? If no values for changed, explain why.
<br>By values, we mean specific String s, int s, URI s, and so on. "abc" is a value, 456 is a value, new URI("http://...") is a value, and so on.
### Example 2
After adding the request "/add-message?s=How are you" we get this page:
![Image] ()
- Which methods in your code are called?
- What are the relevent arguments to those methods, and the values of any relevent fields of the class?
- How do the values of any relevent fields of the class change from this specific request? If no values for changed, explain why.
<br>By values, we mean specific String s, int s, URI s, and so on. "abc" is a value, 456 is a value, new URI("http://...") is a value, and so on.
<br>Here is a screenshot of the StringServer.java code
![Image] ()

## Part 2
Using the command line, show with ls and take screenshots of:
- The path to the private key for your SSH key for logging into ieng6 (on your computer or on the home directory of the lab computer)
- The path to the public key for your SSH key for logging into ieng6(within your account on ieng6)
- A terminal interation where you log into ieng6 with your course specific account without being asked for a password

## Part 3
In a couple of sentences, describe something you learned from lab in week 2 or 3 that you did'nt know before.
