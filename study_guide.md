

1. **What does it mean that network reliability is engineered?**

   rely on protocols that make up the layers 

2. **Give an overview of the Application Layer.**

   Both the TCP/IP model and the OSI model define an Application layer as the topmost layer in their respective layered systems (the Session layer and the Presentation layer also in OSI). Something to be clear about here is that the application layer is not the *application itself*, but rather a set of protocols which provide communication services to applications.

   One thing both models have in common however is that the protocols which exist at the Application layer are the ones with which the application most directly interacts. That's not to say that networked applications are limited to interacting with only Application layer protocols. You can see many applications interacting with Transport layer protocols by, for example, opening a TCP socket. However, it is much less common to build applications that interact directly with protocols below the Transport layer.

   Application layer protocols rely on the protocols at the layers below them to ensure that a message gets to where it is supposed to, and focus instead on the structure of that message and the data that it should contain.

   We can perhaps think of Application layer protocols as being the rules for how applications talk to each other at a syntactical level. Different types of applications have different requirements with regards to how they communicate at a syntactical level, and so as a result there are many different protocols that exist at the application layer. For example, the rules for how an email client communicates with an email server will be different from the rules for how a web browser communicates with a web server because emails and web pages are fundamentally different things serving different purposes.

3. **What is HTML?**

   - Primary protocol used for communication on the Web. 
     - Internet is a network of networks (infrastructure that enables inter-network communication, both in terms of the physical network and the lower-level protocols that control its use) while the web is a service that can be accessed via the internet.
     - In simple terms it is a vast information system comprised of resources which are navigable by means of a URL (Uniform Resource Locator). HTTP is closely tied, both historically and functionally, to the web as we know it. It is the primary means by which applications interact with the resources which make up the web.
     - The means of providing that uniformity in the earliest incarnation of the Web was essentially a combination of three technologies or concepts: HTML, URIs, and HTTP.
     - **Hypertext Markup Language** (HTML) was the means by which the resources in this system should be uniformly structured. This early version of HTML was intended for structuring text documents using headings, paragraphs, and lists. It was very basic, containing only 18 elements. The most revolutionary of these elements was the anchor elements `<A>`, which uses a `href` attribute to provide a link from one resource to another. We'll explore HTML in a lot more detail in a later course.

4. **DNS**

   - The *Domain Name System* (DNS) is a distributed database which *translates a domain name* such as `google.com` *to an IP Address* such as `216.58.213.14`.

     

   Mapping from URL to IP address is handled by the Domain Name System or **DNS**. DNS is a distributed database which translates domain names like `www.google.com` to an IP address, so that the IP address can then be used to make a request to the server. Stated differently, it keeps track of domain names and their corresponding IP addresses on the Internet. So an address like `www.google.com` might be resolved to an IP address `197.251.230.45`.  Stored on computers called **DNS servers**.

   


4. **What is HTTP?**

   1. The most common client is an application you interact with on a daily basis called a **Web Browser**. Examples of web browsers include Internet Explorer, Firefox, Safari and Chrome, including mobile versions. Web browsers are responsible for issuing HTTP requests and processing the HTTP response in a user-friendly manner onto your screen. Web browsers aren't the only clients around, as there are many tools and applications that can also issue HTTP requests.
   2. text- based protocol from client to server and back
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

   - **Client:** When we talk the word **Client**, it mean to talk of a person or an organization using a particular service. Similarly in the digital world a **Client**is a computer (**Host**) i.e. capable of receiving information or using a particular service from the service providers (**Servers**).
   - **Servers:** Similarly, when we talk the word **Servers**, It mean a person or medium that serves something. Similarly in this digital world a **Server** is a remote computer which provides information (data) or access to particular services.

   So, its basically the **Client** requesting something and the **Server** serving it as long as its present in the database.



1. **What are HTTP requests and responses? What are the components of each?**

   If you're fuzzy on the previous paragraph, read it again. It's critical to understand that when using a browser, the browser hides a lot of the underlying HTTP request/response cycle from you. Your browser issued the initial `POST` request, got a response with a `Location` header, then issued another request without any action from you, then displayed the response from that second request. Once again, if you were using a pure HTTP tool, you'd see the `Location` response header from the first `POST` request, but the tool would not automatically issue a second request for you. (Some HTTP tools have this ability, if you check the "automatically follow redirects" option.)



Response Header - 

1. **Describe the HTTP request/response cycle.**

   The most important components to understand about an HTTP request are:

   - HTTP method ex/GET
   - path
   - headers
   - message body (for `POST` requests)
     - connection is established via TCP
     - HTTP GET request sent
     - response retrieved
     - TCP connection closed

2. **What is a state in the context of the 'web'?**

   Visual appearance is an effect of statefulness. Feeling of persistence of a stateful connection. Shopping cart experience. 

   

3. **What is statelessness?**

   A protocol is said to be **stateless** when it's designed in such a way that each request/response pair is completely independent of the previous one. It is important to be aware of HTTP as a stateless protocol and the impact it has on server resources and ease of use. In the context of HTTP, it means that the server does not need to hang on to information, or state, between requests. As a result, when a request breaks en route to the server, no part of the system has to do any cleanup. Both these reasons make HTTP a resilient protocol, as well as a difficult protocol for building stateful applications. Since HTTP, the protocol of the internet, is inherently stateless that means web developers have to work hard to simulate a stateful experience in web applications.

4. **What is a stateful Web Application?**

   When you go to Facebook, for example, and log in, you expect to see the internal Facebook page. That was one complete request/response cycle. You then click on the picture -- another request/response cycle -- but you do not expect to be logged out after that action. If HTTP is stateless, how did the application maintain state and remember that you already input your username and password? In fact, if HTTP is stateless, how does Facebook even know this request came from *you*, and how does it differentiate data from you vs. any other user? There are tricks web developers and frameworks employ to make it seem like the application is stateful, but those tricks are beyond the scope of this book. The key concept to remember is that even though you may feel the application is stateful, underneath the hood, the web is built on HTTP, a stateless protocol. It's what makes the web so resilient, distributed, and hard to control. It's also what makes it so difficult to secure and build on top of.

5. **How can we mimic a stateful application?**

   - Sessions
   - Cookies
   - Asynchronous JavaScript calls, or AJAX
   - One way to accomplish this is by having the server send some form of a unique token to the client. Whenever a client makes a request to that server, the client appends this token as part of the request, allowing the server to identify clients. In web development, we call this unique token that gets passed back and forth the **session identifier**.
   - This mechanism of passing a `session id` back and forth between the client and server creates a sense of persistent connection between requests. Web developers leverage this faux statefulness to build sophisticated applications. Each request, however, is technically stateless and unaware of the previous or the next one.
   - This sort of faux statefulness has several consequences. First, every request must be inspected to see if it contains a session identifier. Second, if this request does, in fact, contain a session id, the server must check to ensure that this session id is still valid. The server needs to maintain some rules with regards to how to handle session expiration and also decide how to store its session data. Third, the server needs to retrieve the session data based on the session id. And finally, the server needs to recreate the application state (e.g., the HTML for a web request) from the session data and send it back to the client as the response.
   - This means that the server has to work very hard to simulate a stateful experience, and every request still gets its own response, even if most of that response is identical to the previous response.

6. **Why HTTP makes it difficult to build a stateful application?**

   This *statelessness* is what makes HTTP and the internet so distributed and difficult to control, but it's also the same ephemeral attribute that makes it difficult for web developers to build **stateful** web applications.

   

7. **How the idea that HTTP is a stateless protocol makes the web difficult to secure?**

   1. Connection is broken once the request/response cycle is complete
   2. This *statelessness* is what makes HTTP and the internet so distributed and difficult to control, but it's also the same ephemeral attribute that makes it difficult for web developers to build **stateful** web applications.

8. **What is a `GET` request and how does it work?**

   Found in method section of chrome developer tools.  **HTTP Request Method**. You can think of this as the verb that tells the server what action to perform on a resource. The two most common HTTP request methods you'll see are `GET` and `POST`.  When you think about retrieving information, think `GET`, which is the most used HTTP request method. In the above diagram, you'll notice almost all of the requests use `GET` to retrieve the resources needed to display the web page.

   - GET requests are used to retrieve a resource, and most links are GETs.
   - The response from a GET request can be anything, but if it's HTML and that HTML references other resources, your browser will automatically request those referenced resources. A pure HTTP tool will not.

9. **How is `GET` request initiated?**

   retrieving data-`GET` requests are initiated by clicking a link or via the address bar of a browser. When you type an address like `https://www.reddit.com` into the address bar of your browser, you're making a `GET` request. You're asking the web browser to go retrieve the resource at that address, which means we've been making `GET` requests throughout this book. The same goes for interacting with links on web applications. The default behavior of a link is to issue a `GET` request to a URL. 

10. **What is the HTTP response body and what do we use it for?**

    The body contains the data that is being transmitted in an HTTP message and is optional. In other words, an HTTP message can be sent with an empty body. When used, the body can contain HTML, images, audio and so on. You can think of the body as the letter enclosed in an envelope, to be posted.

11. **What are the obligatory components of HTTP requests?**

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

      

12. **What are the obligatory components of HTTP response?**

    The most important parts of an HTTP response are:

    - status code-  only thing Mandatory ex/ 200 OK

    - headers - status and HTTP version - Optional followed by a space 

      - metadata about contents of response ex/ text/html

    - message body, which contains the raw response data (often in HTML)

    - EX/ HTTP/1.1 200 OK

      Content-Type: text/html    =>all a header to see header in terminal type curl -I http://webite/- written in HTML

      ...

13. **Which HTTP method would you use to send sensitive information to a server? Why?**

    Post- pushing data to the server

14. **Describe how would you send a `GET` request to a server and what would happen at each stage.**

    - GET requests are used to retrieve a resource, and most links are GETs.
    - The response from a GET request can be anything, but if it's HTML and that HTML references other resources, your browser will automatically request those referenced resources. A pure HTTP tool will not.
    - `GET` requests are initiated by clicking a link or via the address bar of a browser. When you type an address like `https://www.reddit.com` into the address bar of your browser, you're making a `GET` request. You're asking the web browser to go retrieve the resource at that address, which means we've been making `GET` requests throughout this book. The same goes for interacting with links on web applications. The default behavior of a link is to issue a `GET` request to a URL

15. **Describe how would you send `POST` requests to a server and what is happening at each stage.**

    1. **`GET` requests should only retrieve content from the server.** They can generally be thought of as "read only" operations, however,  there are some subtle exceptions to this rule. For example, consider a  webpage that tracks how many times it is viewed. `GET` is still appropriate since the main content of the page doesn't change.

       **`POST` requests involve changing values that are stored on the server.** Most HTML forms that submit their values to the server will use `POST`. Search forms are a noticeable exception to this rule: they often use `GET` since they are not changing any data on the server, only viewing it

    `POST` is used when you want to initiate some action on the server, or send data to a server. Let's see an example with our HTTP tool: Typically from within a browser, you use `POST` when submitting a form. `POST`requests allow us to send much larger and sensitive data to the server, such as images or videos. For example, say we need to send our username and password to the server for authentication. We could use a `GET` request and send it through query strings. The flaw with this approach is obvious: our credentials become exposed instantly in the URL; that isn't what we want. Using a `POST` request in a form fixes this problem. `POST` requests also help sidestep the query string size limitation that you have with `GET` requests. With `POST` requests, we can send significantly larger forms of information to the server.

16. **What is a status code? What are some of the status codes types? What is the purpose of status codes?**

    Server always responds with a status code- Do I have the files that the client wants?- sends a response yes/no. 3 digit number to let the client know if they were found/not found/error/etc.. 1XX= Informational, 2XX= Successful, 3XX= Redirection, 4XX= Client Error(404 not found), 5XX= Server Error 

    *  The first component we'll look at is the HTTP Status Code. The status code is a three-digit number that the server sends back after recieving a request signifying the status of a request.  The status text displayed next to the status code provides the description of the code. 

17. **Imagine you are using an HTTP tool and you received a status code `302`. What does this status code mean and what happens if you receive a status code like that?**

    3XX Redirection ..Status Code. I don't have it but I'll send you somewhere that does. 

    Status Text = Found 'redirect'

    Meaning = The requested resource has changed temporarily. Usually results in a redirect to another URL

    Resource has been moved. Reroute request from original URL to another.

    When your browser sees a response status code of *302*, it knows that the resource has been moved, and will automatically follow the new re-routed URL in the `Location` response header. In this section, we'll focus on redirects in the context of a Browser and an HTTP tool.

    Ex/

    Say you want to access the account profile at [GitHub](http://www.github.com/), you'll have to go to the address `https://github.com/settings/profile`. However, in order to have access to the profile page, you must first be signed in. If you're not already signed in, the browser will send you to a page to do that. After you enter your credentials, you'll be redirected to the original page you were trying to access. This is a pretty common workflow most web applications employ. Let's see how the browser and the HTTP tool handle that workflow.

18. **How do modern web applications 'remember' state for each client?**

    - Sessions- Actual session data is stored on the server.
    - Cookies- A piece of data that's sent from the server and stored in the client during a request/ response cycle.  aka "HTTP cookie" are small files stored in the browser and contain the session info. Server sends session infoand sets it in your browser cookie on your local computer. Client side cookie is compared with the server-side session data on each request to identify the current session. When you visit the same website again, your session will be recognized bc of the stored cookie with its associated info.  After the client sends a request, the server sends a response with a cookie, the client sends another response with that cookie 
      -  This piece of data will be sent to the server each time you make a request and uniquely identifies you -- or more precisely, it identifies your client, which is your browser. The browser on your computer stores these cookies. Now, if you were to close your browser and shut down your computer, the cookie information would still persist.
      - With the session id now being sent with every request, the server can now uniquely identify this client. When the server receives a request with a session id, the server will look for the associated data based on that id, and in that associated session data is where the server "remembers" the state for that client, or more precisely, for that session id.
      - Where is the session data stored? The simple answer is: on the server *somewhere*. Sometimes, it's just stored in memory, while other times, it could be stored in some persistent storage, like a database or key/value store. Where the session data is actually stored is not too important right now. The most important thing is to understand that the session id is stored on the client, and it is used as a "key" to the session data stored server side. That's how web applications work around the statelessness of HTTP.
      - It is important to be aware of the fact that the id sent with a session is unique and expires in a relatively short time. In this context, it means you'll be required to login again after the session expires. If we log out, the session id information is gone:  To recap, we've seen that the session data is generated and stored on the server-side and the session id is sent to the client in the form of a cookie.
    - Asynchronous JavaScript calls and XML, or AJAX

19. **What role does AJAX play in displaying dynamic content in web applications?**

    Its main feature is that it allows browsers to issue requests and process responses *without a full page refresh*. For example, if you're logged into Facebook, the server has to generate the initial page you see, and the response is a pretty complex and  expensive HTML page that your browser displays. The Facebook server has  to add up all the likes and comments for every photo and status, and  present it in a timeline for you. As we described earlier, it's a very  expensive page to re-generate for every request (remember, every action  you take -- clicking a link, submitting a form -- issues a new request).

    When AJAX is used, all requests sent from the client are performed *asynchronously*, which just means that the page doesn't refresh. Let's see an example by performing some search on google:

    The responses from these requests are being processed by some callback. You can think of a `callback` as a piece of logic you pass on to some function to be executed after a certain event has happened. In this case, the callback is triggered  when the response is returned. You can probably guess that the callback  that's processing these asynchronous requests and responses is updating  the HTML with new search results.

20. **Describe some of the security threats and what can be done to minimize them?**

    THREAT - If a malicious hacker was attached to the same network, they could employ *packet sniffing* techniques to read the messages being sent back and forth. As we  learned previously, requests can contain the session id, which uniquely  identifies you to the server, so if someone else copied this session id, they could craft a request to the server and pose as your client, and  thereby automatically being logged in without even having access to your username or password.

    MINIMIZE THREAT - This is where Secure HTTP, or **HTTPS**, helps. A resource that's accessed by HTTPS will start with `https://` instead of `http://`, and usually be displayed with a lock icon in most browsers: With HTTPS every request/response is encrypted before being transported  on the network. This means if a malicious hacker sniffed out the HTTP  traffic, the information would be encrypted and useless.



​		THREAT - if an attacker gets a hold of the session id, both the attacker and the  user now share the same session and both can access the web application. In session hijacking, the user won't even know an attacker is accessing his or her session without ever even knowing the username or password

​	   MINIMIZE THREAT - 

			* One popular way of solving session hijacking is by resetting sessions.  With authentication systems, this means a successful login must render  an old session id invalid and create a new one. With this in place, on  the next request, the victim will be required to authenticate. At this  point, the altered session id will change, and the attacker will not be  able to have access. Most websites implement this technique by making  sure users authenticate when entering any potentially sensitive area,  such as charging a credit card or deleting the account.
			* Another useful solution is by setting an expiration time on sessions.  Sessions that do not expire give an attacker an infinite amount of time  to pose as the real user. Expiring sessions after, say 30 minutes, gives the attacker a far narrower window to access the app.
			* Finally, as we have already covered, another approach is to use HTTPS across the entire app to minimize the chance that an attacker can get  to the session id.



​		THREAT- Cross-site scripting, or **XSS**. This type of attack  happens when you allow users to input HTML or JavaScript that ends up  being displayed by the site directly.  Attackers can craft ingeniously malicious HTML and JavaScript and be  very destructive to both the server as well as future visitors of this  page. For example, an attacker can use JavaScript to grab the session id of every future visitor of this site and then come back and assume  their identity. It could happen silently without the victims ever  knowing about it. Note that the malicious code would bypass the  same-origin policy because the code lives on the site.

MINIMIZE THREAT - 

	* One way to prevent this kind of attack is by making sure to always  sanitize user input. Eliminate problematic input, such as <script> tags, or disallowing HTML and JavaScript input altogether in favor of a safer format, like Markdown.
	* The second way to guard against XSS is to escape all user input data  when displaying it. If you do need to allow users to input HTML and  JavaScript, then when you print it out, make sure to escape it so that  the browser does not interpret it as code.

 




1. **What is the Same Origin Policy? How it is used to mitigate certain security threats?**

   The same-origin policy is an important concept that permits unrestricted interaction between resources originating from the same origin, but  restricts certain interactions between resources originating from  different origins. What we mean by *origin* here is the combination of a url's scheme, hostname, and port. So `http://mysite.com/doc1` would be considered to have the same origin as `http://mysite.com/doc2`, but a different origin to `https://mysite.com/doc2` (different scheme), `http://mysite.com:4000/doc2` (different port), and `http://anothersite.com/doc2` (different host).

   Same-origin policy doesn't restrict *all* cross-origin requests.  Requests such as linking, redirects, or form submissions to different  origins are typically allowed. Also typically allowed is the embedding  of resources from other origins, such as scripts, css stylesheets,  images and other media, fonts, and iframes. What *is* typically restricted are cross-origin requests where resources are being accessed programmatically using APIs such as `XMLHttpRequest` or `fetch` (the details of which are beyond the scope of this book).   

2. **What determines whether a request should use `GET` or `POST` as its HTTP method?**

   1. 2 distinct behaviors 


​		GET- accessing info from resource 

​        POST- form submission/providing credentials/ modifying info server side 

​		

1. **What is the relationship between a scheme and a protocol in the context of a URL?**

   Another frequent point of confusion when discussing URLs are the terms *scheme* and *protocol*. When looking at URL Components, we described the component that  prepends the colon and two forward slashes at the start of a URL as the *scheme*.

   You'll often hear this URL component incorrectly referred to as the *protocol*. The source of this confusion is that, although referring to this  component as the protocol is technically incorrect, in the context of a  URL there *is* a relationship between the two things in that the  scheme identifies which protocol should be used to access the resource.  It should be noted that 'protocol' in this sense refers to a 'family' of protocols, rather than a specific protocol version, e.g. `HTTP` rather than `HTTP 1.0` or `HTTP 1.1`.

   One more thing to note when discussing schemes and protocols is that the canonical form of a scheme name is lowercase. The convention is to  refer to scheme names in lowercase, e.g. `http`, and protocol names in uppercase, e.g. HTTP.

2. **In what ways can we pass information to the application server via the URL?**

3. **How insecure HTTP message transfer looks like?**

4. **What services does HTTP provide and what are the particular problems each of them aims to address?**

   framework for comm over internet fast, extensible(build on top), web frameworks interact with HTTP

5. **TLS HANDSHAKE STEPS**

   TLS assumes TCP is being used at the Transport layer, and the TLS Handshake takes place after the TCP Handshake. A step-by-step description of the TLS Handshake process might look something like this:

   1. The TLS Handshake begins with a `ClientHello` message which is sent immediately after the TCP `ACK`. Among other things, this message contains the maximum version of the TLS protocol that the client can support, and a list of Cipher Suites that the client is able to use (we'll discuss Cipher Suites a little later on).
   2. On receiving the `ClientHello` message, the server responds with a message of its own. This message includes a `ServerHello`, which sets the protocol version and Cipher Suite, as well as other related information. As part of this message the server also sends its certificate (which contains its public key), and a `ServerHelloDone` marker which indicates to the client that it has finished with this step of the handshake.
   3. Once the client has received the `ServerHelloDone` marker, it will initiate the key exchange process. It's this key exchange process that ultimately enables both the client and server to securely obtain a copy of the symmetric encryption key that will be used for the bulk of the secure message transfer between the two parties. The exact process for generating the symmetric keys will vary depending on which key exchange algorithm was selected as part of the Cipher Suite (e.g. RSA, Diffie-Hellman, etc). You don't need to worry about the distinctions between these key exchange mechanisms, but as an example RSA works in the following way:
      - The client generates what's known as a 'pre-master secret', encrypts it using the server's public key, and sends it to the server.
      - The server will receive the encrypted 'pre-master secret' and decrypt it using its private key.
      - Both client and server will use the 'pre-master' secret, along with some other pre-agreed parameters, to generate the same symmetric key.
      - As part of the communication which includes the `ClientKeyExchange` message (e.g. the pre-master secret), the client also sends a `ChangeCipherSpec` flag, which tells the server that encrypted communications should now start using the symmetric keys. Additionally this communication includes a `Finished` flag to indicate that the client is now done with the TLS Handshake.
   4. The server also sends a message with `ChangeCipherSpec` and `Finished` flags. The client and server can now begin secure communication using the symmetric key.

   

   ![Graphic illustrating the steps of TLS Handshake](https://da77jsbdz4r05.cloudfront.net/images/ls170/tls-encryption-tls-handshake.png)

   

   As you can see, the TLS Handshake is a fairly complicated process. We certainly don't expect you to memorize every detail of the various steps involved. Instead, try to form a high-level mental model for how it works. Note also that the exact process will vary according to which version of TLS is used. The key points to remember about the TLS Handshake process is that it is used to:

   - Agree which version of TLS to be used in establishing a secure connection.
   - Agree on the various algorithms that will be included in the cipher suite.
   - Enable the exchange of symmetric keys that will be used for message encryption.

   Something you should be aware of is that one of the implications of this complexity is its impact on performance. The TLS handshake can add up to two round-trips of latency (depending on the TLS version) to the establishment of a connection between client and server prior to the point where any application data can be sent. This is on top of the initial round trip resulting from the TCP Handshake.

6. **What is symmetric key encryption? What is it used for?**

   

7. **What is asymmetric key encryption? What is it used for?**

   Happens at TLS Handshake before messages are sent.  Encrypts keys for end to end encryption. 

8. **Describe SSL/TLS encryption process.**

   HTTPS sends messages through a cryptographic protocol called [TLS](http://en.wikipedia.org/wiki/Transport_Layer_Security) for encryption. Earlier versions of HTTPS used `SSL`or Secure Sockets Layer until `TLS` was developed. These cryptographic protocols use certificates to  communicate with remote servers and exchange security keys before data  encryption happens. You can inspect these certificates by clicking on  the padlock icon that appears before the `https://`:

   To securely send messages via HTTP we want both the request *and* the response to be encrypted in a such a way that they can only be decrypted by the intended recipient. The most efficient way to do this is via symmetric key cryptography. If we want to use symmetric keys however, we also need a way to securely exchange the symmetric key.

9. **Describe the pros and cons of TLS Handshake**

   The way in which TLS (Transport Leyer Security) sets up an encrypted connection is via a process known as the TLS Handshake.  The clever thing about TLS is the way that it uses a combination of symmetric and asymmetric cryptography.  The clever thing about TLS is the way that it uses a combination of symmetric and asymmetric cryptography

   ​	Why? Cryptography- techniques to secure communication

     - encryption keys- you can only decipher the message with an encryption key that both sides agree on and copy/ we can now encrypt and decrypt
     - No one else can have the key! How can we exchange this key without anyone else getting it? We must encrypt the encryption key![Simple Alice and Bob graphic illustrating the mechanics of asymmetric key encryption](https://da77jsbdz4r05.cloudfront.net/images/ls170/tls-encryption-asymmetric.png)
     - Asymmetric Key Encryption- 
       - aka public key encyrption uses a pair of keys- a public key and a private key.
       - Unlike the symmetric system where the same key is used to encrypt and decrypt messages, in the asymmetric system the keys in the pair are non-identical: the public key is used to encrypt and the private key to decrypt.
       - The important thing to understand is that messages encrypted with the public key can *only* be decrypted with the private key. The public key is made openly available but the private key is kept in the sole possession of the message receiver.
       - An important thing to note here is that this encryption is primarily intended to work in one direction. Bob can send Alice messages encrypted with the public key which she can then decrypt with the private one. The same key pair would not be used in the other direction for secure communication, since anyone with access to the public key can decrypt the message.

![Simple Alice and Bob graphic illustrating the mechanics of asymmetric key encryption](https://da77jsbdz4r05.cloudfront.net/images/ls170/tls-encryption-asymmetric.png)

1. **Why do we need digital TLS/SSL certificates?**

   1. So we don't interact with a false website.

   2. During the description of the TLS Handshake, we mentioned Cipher Suites a few times. So what exactly is a Cipher Suite?

      A *cipher* is a cryptographic algorithm; in other words they are sets of steps for performing encryption, decryption, and other related tasks. A *cipher suite* is a suite, or set, of ciphers.

      TLS uses different ciphers for different aspects of establishing and maintaining a secure connection. There are many algorithms which can be used for performing the key exchange process, as well as for carrying out authentication, symmetric key encryption, and checking message integrity.

      The algorithms for performing each of these tasks, when combined, form the *cipher suite*. The suite to be used is agreed as part of the TLS Handshake. As part of the `ClientHello` message, the client sends a list of algorithms it supports for each required task, and the server chooses from these according to which algorithms it also supports.

      - The server sends its certificate, which includes its *public* key.
      - The server creates a 'signature' in the form of some data encrypted with the server's *private* key.
      - The signature is transmitted in a message along with the original data from which the signature was created.
      - On receipt of the message, the client decrypts the signature using the server's public key and compares the decrypted data to the original version.
      - If the two versions match then the encrypted version could only have been created by a party in possession of the private key.
      - Following a process such as this we can identify that the server which provided the certificate during the initial part of the TLS Handshake as being in possession of the private key, and therefore the actual owner of the certificate.
        * There's still an issue here though. What's to stop a malicious third-party creating their own key pair and certificate identifying them as, say, a well-known bank? Just as it's possible to create a fake ID card in the real world, it's possible to create a fake digital certificate. How are we to know if a certificate is genuine or not? This is where Certificate Authorities come in.

2. **What is CA hierarchy and what is its role in providing secure message transfer?**

   1. So who exactly are these Certificate Authorities, and why should we trust them? There are different 'levels' of CA. An 'Intermediate CA' can be any company or body authorised by a 'Root CA' to issue certificates on its behalf. A widely-used Intermediate CA is Let's Encrypt, who provide free, automated certificates.
   2. Client software, such as browsers, store a list of these authorities along with their Root Certificates (which includes their public key). When receiving a certificate for checking, the browser can go up the chain to the Root Certificate stored in its list.
   3. The purpose of this chain-like structure is the level of security it provides. The private keys of the Root CAs are kept behind many layers of security in order to be kept as inaccessible as possible. As such they don't issue end-user certificates, but leave that up to the Intermediate CAs. Additionally, if the private key of an Intermediate CA somehow became compromised, the root CA can revoke the certificate for Intermediate, therefore invalidating all of the certificates down the chain from it, and simply issue a new one.

3. **What is Cipher Suites and what do we need it for?**

   During the description of the TLS Handshake, we mentioned Cipher Suites a few times. So what exactly is a Cipher Suite?

   A *cipher* is a cryptographic algorithm; in other words they are sets of steps for performing encryption, decryption, and other related tasks. A *cipher suite* is a suite, or set, of ciphers.

   TLS uses different ciphers for different aspects of establishing and maintaining a secure connection. There are many algorithms which can be used for performing the key exchange process, as well as for carrying out authentication, symmetric key encryption, and checking message integrity.

   The algorithms for performing each of these tasks, when combined, form the *cipher suite*. The suite to be used is agreed as part of the TLS Handshake. As part of the `ClientHello` message, the client sends a list of algorithms it supports for each required task, and the server chooses from these according to which algorithms it also supports.

4. **How does TLS add a security layer to HTTP?**

   1. TLS used to be SSL 

   2. 3 important security services that are provided by TLS:

      * Each of these services are important in their own right, but when combined they provide for very secure message exchange over what is essentially an unsecure channel. Let's look a bit more closely at the nature of these services.

      1. *Encryption*-
         1. a process of encoding a message so that it can only be read by those with an authorized means of decoding the message
         2. See TLS Handshake 
      2. *Authentification*-
         1. a process to verify the identity of a particular party in the message exchange
         2. TLS Authentication is implemented through the use of *Digital Certificates*.
         3. Certificates are *signed* by a *Certificate Authority*, and work on the basis of a *Chain of Trust* which leads to one of a small group of highly trusted *Root CAs*
      3. *Integrity*-
         1. a process to detect whether a message has been interfered with or faked
            1. The main field that interests us in terms of providing message integrity is the `MAC` (*Message Authentication Code*- similar to checksum) field. Note that, though they use the same acronym, the Message Authentication Code is completely unrelated to the MAC Address (media access control address) discussed in an earlier lesson. The intention of the `MAC` field in a TLS record is to add a layer of security by providing a means of checking that the message hasn't been altered or tampered with in transit.
               1. The sender will create what's called a *digest* of the data payload. This is effectively a small amount of data derived from the actual data that will be sent in the message. The digest is created using a specific hashing algorithm combined with a pre-agreed hash value. This hashing algorithm to be used and hash value will have been agreed as part of the TLS Handshake process when the Cipher Suite is negotiated.
               2. The sender will then encrypt the data payload using the symmetric key (as described earlier in the Encryption section), encapsulate it into a TLS record, and pass this record down to the Transport layer to be sent to the other party.
               3. Upon receipt of the message, the receiver will decrypt the data payload using the symmetric key. The receiver will then also create a digest of the payload using the same algorithm and hash value. If the two digests match, this confirms the integrity of the message.

5. **Compare HTTP and HTTPS.**

   

6. **Does HTTPS use other protocols?**

7. **How do you know a website uses HTTPS?**

8. **Give examples of some protocols that would be used when a user interacts with a banking website. What would be the role of those protocols?**

   1. TLS

9. **What is server-side infrastructure? What are its basic components?**

   A *web server* is typically a server that responds to requests for static assets: files, images, css, javascript, etc. These requests  don't require any data processing, so can be handled by a simple web  server.

   An *application server*, on the other hand, is typically where application or business logic resides, and is where more complicated  requests are handled. This is where your server-side code lives when  deployed.

   The application server will often consult a persistent *data store*, like a relational database, to retrieve or create data. Data stores can also be simple files, key/value stores, document stores and many other  variations, as long as it can save data in some format for later  retrieval and processing.

10. **What is a server? What is its role?**

    Yet taken together as unified concept, the server-side infrastructure in its entirety is the "server" to the client. The word "server" is  severely overloaded, so it's important to keep in mind what exactly  we're talking about at every turn.

11. **What are optimizations that developers can do in order to improve performance and minimize latency?**

    1. Cache 
    2. reduce TCP connections 
    3. Browser Optimization 
    4. Compression techniques
    5. DNS Optimizations 

# Summary

- 
- 
- 
- 
- A single HTTP message exchange consists of a *Request* and a *Response*. The exchange generally takes place between a *Client* and a *Server*. The client sends a Request to the server and the server sends back a Response.
- An *HTTP Request* consists of a *request line*, *headers*, and an optional *body*.
- An *HTTP Response* consists of a *status line*, optional *headers*, and an optional *body*.
- *Status codes* are part of the status line in a Response. They indicate the status of the request. There are various categories of  status code.
- HTTP is a *stateless* protocol. This means that each Request/  Response cycle is independent of Request and Responses that came before  or those that come after.
- *Statefulness can be simulated* through techniques which use *session IDs*, *cookies*, and *AJAX*.
- HTTP is *inherently insecure*. Security can be increased by using *HTTPS*, enforcing *Same-origin policy*, and using techniques to prevent *Session Hijacking* and *Cross-site Scripting*.

# Summary

- HTTP is a *text-based* protocol. HTTP Request and Responses involve sending text between the client and server
- In order for the protocol to work, the Request and Response must be structured in such a way that both the client and the server can understand them.
- With HTTP/1.1, the end of the headers is indicated by an *empty line*.
- The `Content-Length` header can be used to indicate the *size of the body*. This can help determine where the HTTP message should end.



# Summary

- *HTTP Requests and Responses* are transferred in *plain text*; as such they are *essentially insecure*.
- We can use the *Transport Layer Security* (TLS) Protocol to add security to HTTP communications.
- *TLS encryption* allows us to *encode messages* so that they can only be read by those with an authorized means of decoding the message
- TLS encryption uses a combination of *Symmetric Key Encryption* and *Asymmetric Key Encryption*. Encryption of the initial key exchange is performed asymmetrically, and subsequent communications are symmetrically encrypted.
- The *TLS Handshake* is the process by which a client and a server *exchange encryption keys*.
- The *TLS Handshake* must be performed before secure data exchange can begin; it involves *several round-trips of latency* and therefore has an *impact on performance*.
- A *cipher suite* is the *agreed set of algorithms* used by the client and server during the secure message exchange.
- *TLS authentication* is a means of *verifying the identity* of a participant in a message exchange.
- TLS Authentication is implemented through the use of *Digital Certificates*.
- Certificates are *signed* by a *Certificate Authority*, and work on the basis of a *Chain of Trust* which leads to one of a small group of highly trusted *Root CAs*.
- The server's certificate is *sent* during the *TLS Handshake* process.
- *TLS Integrity* provides a means of *checking* whether a message has been *altered or interfered with* in transit.
- TLS Integrity is implemented through the use of a *Message Authentication Code* (MAC).



# Summary

- HTTP has changed considerably over the years, and is continuing to change.
- Many of the changes to HTTP are focused on improving performance in response to the ever increasing demands of modern networked applications.
- Latency has a big impact on the performance of networked applications. As developers and software engineers we need to be aware of this impact, and try to mitigate against it through the use of various optimizations.
- In building networked applications, there are tools and techniques available to us that work around or go beyond the limitations of basic HTTP request-response functionality.
- For certain use cases a peer-to-peer architecture may be more appropriate than a client-server architecture.

HTTP and GUI need to be installed locally. Otherwise use AWS Cloud9







The top layer of the Internet Protocol Suite (Application) mostly maps to the top three layers of the OSI Model (Application, Presentation, Session).
The second layer of the Internet Protocol Suite (Transport) mostly maps to the fourth layer of the OSI model (Transport)
The third layer of the Internet Protocol Suite (Internet) mostly maps to the fifth layer of the OSI model (Network)
The fourth layer of the Internet Protocol Suite (Link) mostly maps to the bottom two layers of the OSI model (Data Link and Physical)

https://launchschool.com/lessons/4af196b9/assignments/21ef33af