# CSE 15L Lab 2

*Servers and Bugs*

> Part 1
  
 
  
 ![port 5000 working example](Look it works.png)

 ![StringServer.java code](StringServer Code.png)
  
> Part 2
  
> Part 3
  
In lab 2, I learned how to make a web server with Java which is something that I have never done before. I learned that Java has an interface called *URIHandler*. I also learned that Java has a *Server.start()* method which makes creating the web server easy to do because you just pass on the Handler object you are using and what port to host it on locally. You also have to create a special Handler class which implements the URI interface in order to handle requests. You can handle requests on the website, such as interpreting paths, returning text, or making queries, by overriding the *handleRequest()* method in the Handler class. 
