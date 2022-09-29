1. **Give an overview of the Application Layer.**

   Both the TCP/IP model and the OSI model define an Application layer as the topmost layer in their respective layered systems (the Session layer and the Presentation layer also in OSI). Something to be clear about here is that the application layer is not the *application itself*, but rather a set of protocols which provide communication services to applications.

   One thing both models have in common however is that the protocols which exist at the Application layer are the ones with which the application most directly interacts. That's not to say that networked applications are limited to interacting with only Application layer protocols. You can see many applications interacting with Transport layer protocols by, for example, opening a TCP socket. However, it is much less common to build applications that interact directly with protocols below the Transport layer.

   Application layer protocols rely on the protocols at the layers below them to ensure that a message gets to where it is supposed to, and focus instead on the structure of that message and the data that it should contain.

   We can perhaps think of Application layer protocols as being the rules for how applications talk to each other at a syntactical level. Different types of applications have different requirements with regards to how they communicate at a syntactical level, and so as a result there are many different protocols that exist at the application layer. For example, the rules for how an email client communicates with an email server will be different from the rules for how a web browser communicates with a web server because emails and web pages are fundamentally different things serving different purposes.

   

2. **What is HTML?**

   - Primary protocol used for communication on the Web. 

     - Internet is a network of networks (infrastructure that enables inter-network communication, both in terms of the physical network and the lower-level protocols that control its use) while the web is a service that can be accessed via the internet.

     - In simple terms it is a vast information system comprised of resources which are navigable by means of a URL (Uniform Resource Locator). HTTP is closely tied, both historically and functionally, to the web as we know it. It is the primary means by which applications interact with the resources which make up the web.

     - The means of providing that uniformity in the earliest incarnation of the Web was essentially a combination of three technologies or concepts: HTML, URIs, and HTTP.

     - **Hypertext Markup Language** (HTML) was the means by which the resources in this system should be uniformly structured. This early version of HTML was intended for structuring text documents using headings, paragraphs, and lists. It was very basic, containing only 18 elements. The most revolutionary of these elements was the anchor elements `<A>`, which uses a `href` attribute to provide a link from one resource to another. We'll explore HTML in a lot more detail in a later course.

       

3. **DNS**

   - The *Domain Name System* (DNS) is a distributed database which *translates a domain name* such as `google.com` *to an IP Address* such as `216.58.213.14`.

     

   Mapping from URL to IP address is handled by the Domain Name System or **DNS**. DNS is a distributed database which translates domain names like `www.google.com` to an IP address, so that the IP address can then be used to make a request to the server. Stated differently, it keeps track of domain names and their corresponding IP addresses on the Internet. So an address like `www.google.com` might be resolved to an IP address `197.251.230.45`.  Stored on computers called **DNS servers**.

   

4. **What is HTTP?**

* A single HTTP message exchange consists of a *Request* and a *Response*. The exchange generally takes place between a *Client* and a *Server*. The client sends a Request to the server and the server sends back a Response.
* HTTP is a *text-based* protocol. HTTP Request and Responses involve sending text between the client and server
* In order for the protocol to work, the Request and Response must be structured in such a way that both the client and the server can understand them.
* Framework for communication over internet- fast, extensible(build on top), web frameworks interact with HTTP

1. The most common client is an application you interact with on a daily basis called a **Web Browser**. Examples of web browsers include Internet Explorer, Firefox, Safari and Chrome, including mobile versions. Web browsers are responsible for issuing HTTP requests and processing the HTTP response in a user-friendly manner onto your screen. Web browsers aren't the only clients around, as there are many tools and applications that can also issue HTTP requests.
2. text- based protocol from client to server and back
   1. HTTP is based on the *client-server* paradigm, in which a client (usually some kind of browser) makes a *request* through the network for a particular web resource stored on a server.
   2. The server, then, sends a *response* to this request that ideally contains the requested resource, or if not, some kind of messaging that explained what happened.
      - The server's response provides the client with the requested  resource, informs the client that the action requested has been carried  out, or else informs the client that an error occured in the process.
3. HTTP is at the core of what the web is about, and also at the core of dynamic web applications. Understanding HTTP is central to understanding how modern web applications work and how they're built.

**Hypertext Transfer Protocol** (HTTP) is the set of rules which provide uniformity to the way resources on the web are transferred between applications. It is a system of rules, a protocol, that serve as a link between applications and the transfer of [hypertext](http://en.wikipedia.org/wiki/Hypertext) documents. Stated differently, it's an agreement, or message format, of how machines communicate with each other. HTTP follows a simple model where a client makes a **request** to a server and waits for a **response**. Hence, it's referred to as a **request response protocol**. 

* Under your browser's hood lies a collection of files -- CSS, HTML, Javascript, videos, images, etc. -- that makes displaying the page possible. All these files were sent from a **server** to your browser, the **client**, by an application protocol called HTTP (yes, this is why URLs in your browser address bar start with "http://").

  

5. **What is the role of HTTP?**

TCP is the protocol that establishes the connection, then HTTP is the command language. Client and server communicate with this language.

At its core, HTTP is a set of rules concerned with the syntax and  structure of messages exchanged between applications. Working with HTTP  is ultimately about understanding what those rules mean, and knowing how and when to apply them.

One of the fundamental aspects of HTTP is its Request-Response behavior. 



6. **Explain the client-server model of web interactions, and the role of HTTP as a protocol within that model**

An example of one way to do things, not the only one. Most prescribe to this model. 

The Client-server model is a distributed application structure that partitions task or workload between the providers of a resource or service, called servers, and service requesters called clients. In the client-server architecture, when the client computer sends a request for data to the server through the internet, the server accepts the requested process and deliver the data packets requested back to the client. Clients do not share any of their resources. Examples of Client-Server Model are Email, World Wide Web, etc.

**How the Client-Server Model works ?**
In this article we are going to take a dive into the **Client-Server** model and have a look at how the **Internet** works via, web browsers. This article will help us in having a solid foundation of the WEB and help in working with WEB technologies with ease.

- **Client:** When we talk the word **Client**, it mean to talk of a person or an organization using a particular service. Similarly in the digital world a **Client** is a computer (**Host**) i.e. capable of receiving information or using a particular service from the service providers (**Servers**).
- **Servers:** Similarly, when we talk the word **Servers**, It mean a person or medium that serves something. Similarly in this digital world a **Server** is a remote computer which provides information (data) or access to particular services.

So, its basically the **Client** requesting something and the **Server** serving it as long as its present in the database.



7. **What are HTTP requests and responses? What are the components of each?**

* An *HTTP Request* consists of a *request line*, *headers*, and an optional *body*.

  * An HTTP request is a text-based message sent from the client to the serve with the aim of accessing a resource on the server.

  * Entering something into the browser address bar, clicking a link,  submitting a form, or any number of other "user interaction" with a  resources on the web can instigate the sending on an HTTP request.

  * **What is a `GET` request and how does it work?**

    Found in method section of chrome developer tools.  **HTTP Request Method**. You can think of this as the verb that tells the server what action to perform on a resource. The two most common HTTP request methods you'll see are `GET` and `POST`.  When you think about retrieving information, think `GET`, which is the most used HTTP request method. In the above diagram, you'll notice almost all of the requests use `GET` to retrieve the resources needed to display the web page.

    - GET requests are used to retrieve a resource, and most links are GETs.
    - The response from a GET request can be anything, but if it's HTML and that HTML references other resources, your browser will automatically request those referenced resources. A pure HTTP tool will not.

  * **How is `GET` request initiated?**

    retrieving data-`GET` requests are initiated by clicking a link or via the address bar of a browser. When you type an address like `https://www.reddit.com` into the address bar of your browser, you're making a `GET` request. You're asking the web browser to go retrieve the resource at that address, which means we've been making `GET` requests throughout this book. The same goes for interacting with links on web applications. The default behavior of a link is to issue a `GET` request to a URL. 

* An *HTTP Response* consists of a *status line*, optional *headers*, and an optional *body*.

  * An HTTP response consists of a *response line*, *headers*, and a *body*
  * The response line contains the status code, status text, and version
    - The status code is a three digit number indicating the specific status of the response, i.e. whether or not it was successful
    - It is accompanied by the status text that tells the status of the response
  * HTTP response headers contain additional information about the response
    - information about the type of encoding used the data
    - the name of the server
    - a new resource location if applicable (`Location` header), which helps the client *redirect* to the requested resource if it has been moved
    - the `content-type` (i.e. `text/html`), which helps the client correctly render the data in a user friendly way
  * The HTTP response body consists of the raw data for the requested resource
    - This might be the HTML of the webpage, or the raw data of any files being requested, such as images, videos, or audio files
    - The body contains the data that is being transmitted in an HTTP message and is optional. In other words, an HTTP message can be sent with an empty body. When used, the body can contain HTML, images, audio and so on. You can think of the body as the letter enclosed in an envelope, to be posted.

It's critical to understand that when using a browser, the browser hides a lot of the underlying HTTP request/response cycle from you. Your browser issued the initial `POST` request, got a response with a `Location` header, then issued another request without any action from you, then displayed the response from that second request. Once again, if you were using a pure HTTP tool, you'd see the `Location` response header from the first `POST` request, but the tool would not automatically issue a second request for you. (Some HTTP tools have this ability, if you check the "automatically follow redirects" option.)



8. **What are the obligatory components of HTTP requests?**

   The most important components to understand about an HTTP request are:

   - HTTP method- GET/ POST/DELETE/LISTEN (Action)- required 

   - path - required 

   - Parameters

   - headers

   - message body (for `POST` requests)

   - ex/. GET /(can be more /zuck) HTTP/1.1

     HOST: WWW.HARVARD.EDU

     ....

     ​	* The HTTP method and the path are required, and form part of what is  known as the start-line or request-line. As of HTTP 1.0, the HTTP  version also forms part of the request-line. The `Host` header is a required component since HTTP 1.1. Parameters, all other headers, and message body are optional.

     Technically speaking the 'path' portion of the request-line is known  as the 'request-URI', and incorporates the actual path to the resource  and the optional parameters if present. In practice, most people simply  refer to this part of the request-line as the 'path'.

     A client MUST send a Host header field in all HTTP/1.1 request messages.

     Ex/

     ```ruby 
     GET / HTTP/1.1
     Host: launchschool.com
     ```

     

     CHECK IT: 

     What does it consist of?

     - An HTTP request consists of a *request line*, *headers*, and an optional *body*.

     - The HTTP request line contains the method, path, and version

       - The **method** indicates what kind of action the request is performing (for example, `GET` or `POST`).
       - The **path** indicates where to find the particular resource locally within the server.
       - The **version** tells us which version of HTTP is being used (i.e. 1.0, 1.1, 2)

     - HTTP headers are a way to give more information about both the client and the resource that is being requested

       - The host header:
         - has bee required since HTTP 1.1
         - indicates where the resource in question is located as a server may contain many hosts
       - Other headers might include:
         - fields about what languages are accepted by the client
         - specially formatted string that identifies the client such as a `session id`
         - information about cookies that help applications maintain the appearance of state
         - what type of connection the client prefers (such as `keep-alive`)

     - The body of an HTTP request contains data that is transmitted with the HTTP request

       - What this looks like depends on the type of request methond sent (i.e. method)

       - The body is mainly used with a `POST` request, which is used to send data to the server

       - Said data is typically included in the body of the request

         

9. **What are the obligatory components of HTTP response?**

   The most important parts of an HTTP response are:

   - status code-  only thing Mandatory ex/ 200 OK

   - headers - status and HTTP version - Optional followed by a space 

     - metadata about contents of response ex/ text/html

   - message body, which contains the raw response data (often in HTML)

   - EX/ HTTP/1.1 200 OK

     Content-Type: text/html    =>all a header to see header in terminal type curl -I http://webite/- written in HTML



10. **Describe the HTTP request/response cycle.**

The most important components to understand about an HTTP request are:

- HTTP method ex/GET

- path

- headers

  - With HTTP/1.1, the end of the headers is indicated by an *empty line*.
  - The `Content-Length` header can be used to indicate the *size of the body*. This can help determine where the HTTP message should end.

- message body (for `POST` requests)

  - connection is established via TCP

  - HTTP GET request sent

  - response retrieved

  - TCP connection closed

    

11. **What is a state in the context of the 'web'?**

Visual appearance is an effect of statefulness. Feeling of persistence of a stateful connection. Shopping cart experience. 

What is meant by 'state' in the context of the web?

- A "stateful" web application is one that maintains knowledge of past interactions.
  - This might include keeping track of individual user accounts and  maintain a "logged in" status accross multiple resource requests and  refreshes.
  - Stateful apps can also keep track of items a user has placed in an online "shopping cart", even over multiple days
  - When your e-mail client identifies you by name and displays some kind of customized greeting, this is also an aspect of "state"
- HTTP is a stateless protocol, meaning that no information is kept on the server between request/response cycles.
  - Each request/response cycle is independent, and has no effect on previous or subsequent cycles
- Stateless protocols are resilient, fast, and flexible as the server  doesn't have to retain any information between each request/response  cycle nor does any part of the system have to perform any clean up.
- However, because of the statelessness of HTTP, it can be very  difficult to simulate a stateful experience and make it seem like a  persistent connection exists as many modern web apps do.



12. **What is statelessness?**

A protocol is said to be **stateless** when it's designed in such a way that each request/response pair is completely independent of the previous one. It is important to be aware of HTTP as a stateless protocol and the impact it has on server resources and ease of use. In the context of HTTP, it means that the server does not need to hang on to information, or state, between requests. As a result, when a request breaks en route to the server, no part of the system has to do any cleanup. Both these reasons make HTTP a resilient protocol, as well as a difficult protocol for building stateful applications. Since HTTP, the protocol of the internet, is inherently stateless that means web developers have to work hard to simulate a stateful experience in web applications.



13. **What is a stateful Web Application?**

When you go to Facebook, for example, and log in, you expect to see the internal Facebook page. That was one complete request/response cycle. You then click on the picture -- another request/response cycle -- but you do not expect to be logged out after that action. If HTTP is stateless, how did the application maintain state and remember that you already input your username and password? In fact, if HTTP is stateless, how does Facebook even know this request came from *you*, and how does it differentiate data from you vs. any other user? There are tricks web developers and frameworks employ to make it seem like the application is stateful, but those tricks are beyond the scope of this book. The key concept to remember is that even though you may feel the application is stateful, underneath the hood, the web is built on HTTP, a stateless protocol. It's what makes the web so resilient, distributed, and hard to control. It's also what makes it so difficult to secure and build on top of.



14. **How can we mimic a stateful application?**

- Sessions

- Cookies

- Asynchronous JavaScript calls, or AJAX

- One way to accomplish this is by having the server send some form of a unique token to the client. Whenever a client makes a request to that server, the client appends this token as part of the request, allowing the server to identify clients. In web development, we call this unique token that gets passed back and forth the **session identifier**.

- This mechanism of passing a `session id` back and forth between the client and server creates a sense of persistent connection between requests. Web developers leverage this faux statefulness to build sophisticated applications. Each request, however, is technically stateless and unaware of the previous or the next one.

- This sort of faux statefulness has several consequences. First, every request must be inspected to see if it contains a session identifier. Second, if this request does, in fact, contain a session id, the server must check to ensure that this session id is still valid. The server needs to maintain some rules with regards to how to handle session expiration and also decide how to store its session data. Third, the server needs to retrieve the session data based on the session id. And finally, the server needs to recreate the application state (e.g., the HTML for a web request) from the session data and send it back to the client as the response.

- This means that the server has to work very hard to simulate a stateful experience, and every request still gets its own response, even if most of that response is identical to the previous response.

- What are mechanisms that we can use to simulate state?

  - **Sessions** are a means of identifying a specific client to a server so that it can be made to *seem* as if a persistent connection exists between HTTP requests/responses

    - The server assigns some kind of unique `session id` to the client.
    - Then, the client includes that `session id` in each request it makes.
    - This allows the server to identify individual clients, and preserve the data associated with each identity.
    - This can be difficult to maintain because each HTTP request must be analyzed for a `session id`.
    - Furthermore, each `session id` must be validated and the server must establish procedures for invalid ids
    - If a `session id` is valid, the server needs to store and retrieve data associated with each `session id`, as well as recreate the state from that data when sending back a response

  - **Cookies** are a way for the browser to  store data sent from the server that helps maintain the appearance of  persistent application state. They work in conjunction with `session id`s.

    - Cookies consist of small files stored in the browser that contain information about the `session id`.
    - These files are stored even if the browser is closed or shut down,  which enables a longer and more consistent appearance of state.
    - The information stored in cookies is sent with each request to the server, then used to "unlock" the correct stored session data
    - This allows the server to recreate the correct state of the  application, and the session id to be recognized each time a website is  visited, even if some time has passed.

  - **AJAX** or Asynchronous JavaScript and XML  enables browsers to issue requests and process responses without have to refresh and reload the current webpage

    - Modern web pages tend to be fairly complex, including dynamically generated content as well as many resource dependencies.

    - Therefore, it behoves us to have a means of responding to both  server data and user actions without having to refresh and reload the  whole page.

    - AJAX enabled this functionality, allowing the client to send and  retrieve information in small pieces that can be used to update the  state of an application without refreshing/reloading, making it much  easier to maintain state.

    - AJAX requests are sent like normal HTTP requests, and the server responds to them with a normal HTTP response.

    - Instead of the browser refreshing to process the HTTP response, it will process the response with a *callback function*, which can update the state of the web app.

      

15. **Why HTTP makes it difficult to build a stateful application?**

This *statelessness* is what makes HTTP and the internet so distributed and difficult to control, but it's also the same ephemeral attribute that makes it difficult for web developers to build **stateful** web applications.



16. **How the idea that HTTP is a stateless protocol makes the web difficult to secure?**

* HTTP is a *stateless* protocol. This means that each Request/  Response cycle is independent of Request and Responses that came before  or those that come after.

1. Connection is broken once the request/response cycle is complete
2. This *statelessness* is what makes HTTP and the internet so distributed and difficult to control, but it's also the same ephemeral attribute that makes it difficult for web developers to build **stateful** web applications.



17. **How do modern web applications 'remember' state for each client?**

    * *Statefulness can be simulated* through techniques which use *session IDs*, *cookies*, and *AJAX*.
    * In building networked applications, there are tools and techniques available to us that work around or go beyond the limitations of basic HTTP request-response functionality.
    * HTTP has changed considerably over the years, and is continuing to change.
    * Many of the changes to HTTP are focused on improving performance in response to the ever increasing demands of modern networked applications.
    * Latency has a big impact on the performance of networked applications. As developers and software engineers we need to be aware of this impact, and try to mitigate against it through the use of various optimizations.
    * For certain use cases a peer-to-peer architecture may be more appropriate than a client-server architecture.

    - Sessions- Actual session data is stored on the server.

    - Cookies- A piece of data that's sent from the server and stored in the client during a request/ response cycle.  aka "HTTP cookie" are small files stored in the browser and contain the session info. Server sends session infoand sets it in your browser cookie on your local computer. Client side cookie is compared with the server-side session data on each request to identify the current session. When you visit the same website again, your session will be recognized bc of the stored cookie with its associated info.  After the client sends a request, the server sends a response with a cookie, the client sends another response with that cookie 

      -  This piece of data will be sent to the server each time you make a request and uniquely identifies you -- or more precisely, it identifies your client, which is your browser. The browser on your computer stores these cookies. Now, if you were to close your browser and shut down your computer, the cookie information would still persist.
      -  With the session id now being sent with every request, the server can now uniquely identify this client. When the server receives a request with a session id, the server will look for the associated data based on that id, and in that associated session data is where the server "remembers" the state for that client, or more precisely, for that session id.
      -  Where is the session data stored? The simple answer is: on the server *somewhere*. Sometimes, it's just stored in memory, while other times, it could be stored in some persistent storage, like a database or key/value store. Where the session data is actually stored is not too important right now. The most important thing is to understand that the session id is stored on the client, and it is used as a "key" to the session data stored server side. That's how web applications work around the statelessness of HTTP.
      -  It is important to be aware of the fact that the id sent with a session is unique and expires in a relatively short time. In this context, it means you'll be required to login again after the session expires. If we log out, the session id information is gone:  To recap, we've seen that the session data is generated and stored on the server-side and the session id is sent to the client in the form of a cookie.

    - Asynchronous JavaScript calls and XML, or AJAX

      

18. **What role does AJAX play in displaying dynamic content in web applications?**

    Its main feature is that it allows browsers to issue requests and process responses *without a full page refresh*. For example, if you're logged into Facebook, the server has to generate the initial page you see, and the response is a pretty complex and  expensive HTML page that your browser displays. The Facebook server has  to add up all the likes and comments for every photo and status, and  present it in a timeline for you. As we described earlier, it's a very  expensive page to re-generate for every request (remember, every action  you take -- clicking a link, submitting a form -- issues a new request).

    When AJAX is used, all requests sent from the client are performed *asynchronously*, which just means that the page doesn't refresh. Let's see an example by performing some search on google:

    The responses from these requests are being processed by some callback. You can think of a `callback` as a piece of logic you pass on to some function to be executed after a certain event has happened. In this case, the callback is triggered  when the response is returned. You can probably guess that the callback  that's processing these asynchronous requests and responses is updating  the HTML with new search results.



19. **Which HTTP method would you use to send sensitive information to a server? Why?**

Post- pushing data to the server



20. **Describe how would you send a `GET` request to a server and what would happen at each stage.**

- GET requests are used to retrieve a resource, and most links are GETs.

- The response from a GET request can be anything, but if it's HTML and that HTML references other resources, your browser will automatically request those referenced resources. A pure HTTP tool will not.

- `GET` requests are initiated by clicking a link or via the address bar of a browser. When you type an address like `https://www.reddit.com` into the address bar of your browser, you're making a `GET` request. You're asking the web browser to go retrieve the resource at that address, which means we've been making `GET` requests throughout this book. The same goes for interacting with links on web applications. The default behavior of a link is to issue a `GET` request to a URL

  

21. **Describe how would you send `POST` requests to a server and what is happening at each stage.**

1. **`GET` requests should only retrieve content from the server.** They can generally be thought of as "read only" operations, however,  there are some subtle exceptions to this rule. For example, consider a  webpage that tracks how many times it is viewed. `GET` is still appropriate since the main content of the page doesn't change.

   **`POST` requests involve changing values that are stored on the server.** Most HTML forms that submit their values to the server will use `POST`. Search forms are a noticeable exception to this rule: they often use `GET` since they are not changing any data on the server, only viewing it

`POST` is used when you want to initiate some action on the server, or send data to a server. Let's see an example with our HTTP tool: Typically from within a browser, you use `POST` when submitting a form. `POST`requests allow us to send much larger and sensitive data to the server, such as images or videos. For example, say we need to send our username and password to the server for authentication. We could use a `GET` request and send it through query strings. The flaw with this approach is obvious: our credentials become exposed instantly in the URL; that isn't what we want. Using a `POST` request in a form fixes this problem. `POST` requests also help sidestep the query string size limitation that you have with `GET` requests. With `POST` requests, we can send significantly larger forms of information to the server.



22. **What determines whether a request should use `GET` or `POST` as its HTTP method?**
    1. 2 distinct behaviors 
    2. What are `GET` and `POST` requests? What are their use cases?
       - A `GET` request is used to *retrieve* some resource from the server.
       - A `POST` request is used whenever you want to *send* something to the server, either to transmit data or to initiate some kind of server side action.
       - Without `POST` requests, we are limited to sending data to the server via query strings
       - There not only have a length limitation, but can also expose sensitive data
       - A `POST` request, on the other hand, allows us to send  larger data (such as images or videos) as well as deal with more  sensitive data such as a username or password
       - Typically a `POST` request will be used when submitting some kind of form or other information (such as user authentication or form submission)
       - A `GET` request will be used when clicking on a link or retrieving a resource (such as a webpage)



23. **What is a status code? What are some of the status codes types? What is the purpose of status codes?**

* *Status codes* are part of the status line in a Response. They indicate the status of the request. There are various categories of  status code.

Server always responds with a status code- Do I have the files that the client wants?- sends a response yes/no. 3 digit number to let the client know if they were found/not found/error/etc.. 1XX= Informational, 2XX= Successful, 3XX= Redirection, 4XX= Client Error(404 not found), 5XX= Server Error 

*  The first component we'll look at is the HTTP Status Code. The status code is a three-digit number that the server sends back after recieving a request signifying the status of a request.  The status text displayed next to the status code provides the description of the code. 

- Status codes are three-digit numbers provided in the response line of an HTTP response.

- They signify the status of the response

- ```
  200
  ```

   OK

  - the request was successfully handled, and the resource has been transmitted
  - all 200 level response codes indicate success

- ```
  302
  ```

   FOUND

  - the requested resource has been moved, and the new location has been found.
  - The new location is provided in the `Location` response header.
  - All 300 level status codes indicate some kind of redirect status
  - When the browser receives the 302 response, it will automatically issue an HTTP request to the updated URL provided in the `Location` header.
  - This, ideally, will result in the HTTP 200 OK response so that the browser can render the resource for the user.

- ```
  404
  ```

   NOT FOUND

  - Indicates the resource in question cannot be found, due to a client error with the request
  - All 400 level status codes indicate various client errors

- ```
  500
  ```

   INTERNAL SERVER ERROR

  - Indicates a generic server-side error took place while trying to retrieve the requested resource.

  - All 500 level status codes indicate server side errors.

    

24. **Imagine you are using an HTTP tool and you received a status code `302`. What does this status code mean and what happens if you receive a status code like that?**

* What are the differences when using a web browser versus using an HTTP tool?
  - When using an HTTP tool, a new request for redirected resources (i.e. a `302` response) will not be issued automatically, as it is with a browser
  - A browser will automatically request all referenced resources (i.e.  dependencies) in the raw data of a response, and an HTTP tool will not
  - A browser will render the row response data in a user friendly way, and an HTTP tool will not

3XX Redirection ..Status Code. I don't have it but I'll send you somewhere that does. 

Status Text = Found 'redirect'

Meaning = The requested resource has changed temporarily. Usually results in a redirect to another URL

Resource has been moved. Reroute request from original URL to another.

When your browser sees a response status code of *302*, it knows that the resource has been moved, and will automatically follow the new re-routed URL in the `Location` response header. In this section, we'll focus on redirects in the context of a Browser and an HTTP tool.

Ex/

Say you want to access the account profile at [GitHub](http://www.github.com/), you'll have to go to the address `https://github.com/settings/profile`. However, in order to have access to the profile page, you must first be signed in. If you're not already signed in, the browser will send you to a page to do that. After you enter your credentials, you'll be redirected to the original page you were trying to access. This is a pretty common workflow most web applications employ. Let's see how the browser and the HTTP tool handle that workflow.

