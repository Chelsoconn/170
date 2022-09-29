1. **What is a URL and what components does it have?**

   URL components include the *scheme*, *host* (or hostname), *port*, *path*, and *query string*.

   * It provides us with a systematic means of locating resources that we are requesting (via an HTTP request).

   * It is the mechanism used by browsers to retrieve any published resource on the web.
   * **URL** stands for *Uniform Resource Locator*. A URL is nothing more than the address of a given unique resource on the Web. In theory, each valid URL points to a unique resource. Such resources can be an HTML page, a CSS document, an image, etc. In practice, there are some exceptions, the most common being a URL pointing to a resource that no longer exists or that has moved. As the resource represented by the URL and the URL itself are handled by the Web server, it is up to the owner of the web server to carefully manage that resource and its associated URL.
   * Enter a URL like [http://www.google.com](http://www.google.com/) into your web browser's address bar.
   * The browser creates an HTTP request, which is packaged up and sent to your device's network interface.
   * If your device already has a record of the IP address for the domain name in its DNS cache, it will use this cached address. If the IP address isn't cached, a DNS request will be made to the Domain Name System to obtain the IP address for the domain.
   * The packaged-up HTTP request then goes over the Internet where it is directed to the server with the matching IP address.
   * The remote server accepts the request and sends a response over the Internet back to your network interface which hands it to your browser.
   * Finally, the browser displays the response in the form of a web page.

![mdn-url-all](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL/mdn-url-all.png)

	1) http: The scheme. It always comes before the colon and two forward slashes and tells the web client how to access the resource. In this case it tells the web client to use the Hypertext Transfer Protocol or HTTP to make a request. Other popular URL schemes are ftp, mailto or git. You may sometimes see this part of the URL referred to as the protocol, and there is a connection between the two things in that the scheme can indicate which protocol (or system of rules) should be used to access the resource; in the context of of a URL however, the correct term for this component is the scheme.
	
	2)  The host. It tells the client where the resource is hosted or located.Building then you want to go to a department "the path"
	
	3) The port or port number. It is only required if you want to use a port other than the default.  Unless a different port number is specified, port 80 will be used by default in normal HTTP requests. To use anything other than the default, one has to specify it in the URL.
	
	4)  The path. It shows what local resource is being requested. This part of the URL is optional.
	
	5) The query string, which is made up of query parameters. It is used to send data to the server. This part of the URL is also optional.



2) **What is a Query string? What it is used for?**

   *Query strings* are used to *pass additional data* to the server during an HTTP Request. They take the form of *name/value pairs* separated by an `=` sign. Multiple name/value pairs are separated by an `&` sign. The start of the query string is indicated by a `?`.

![Query String Components](https://d186loudes4jlv.cloudfront.net/http/images/query_string_components.png)

| Query String Component | Description                                                  |
| :--------------------- | :----------------------------------------------------------- |
| ?                      | This is a reserved character that marks the start of the query string |
| search=ruby            | This is a parameter name/value pair.                         |
| &                      | This is a reserved character, used when adding more parameters to the query string. |
| results=10             | This is also a parameter name/value pair.                    |

In the above example, name/value pairs in the form of `product=iphone`, `size=32gb` and `color=white`are passed to the server from the URL. This is asking the `www.phoneshop.com` server to narrow down on a product `iphone`, size `32gb` and color `white`. How the server uses these parameters is up to the server side application.  **Because query strings are passed in through the URL, they are only used in HTTP GET requests**

Query strings are great to pass in additional information to the server, however, there are some limits to the use of query strings:

- Query strings have a maximum length. Therefore, if you have a lot of data to pass on, you will not be able to do so with query strings.

- The name/value pairs used in query strings are visible in the URL. For this reason, passing sensitive information like username or password to the server in this manner is not recommended.

- Space and special characters like `&` cannot be used with query strings. They must be URL encoded

  

  

  3) **What URL encoding is and when it might be used for?**

  - *URL encoding* is a technique whereby *certain characters* in a URL are *replaced with an ASCII code*.
  - URL encoding is used if a character has no corresponding character in the ASCII set, is unsafe because it is used for encoding other  characters, or is reserved for special use within the url.

  URLs are designed to accept only certain characters in the standard 128-character [ASCII character set](http://en.wikipedia.org/wiki/ASCII). Reserved or unsafe ASCII characters which are not being used for their intended purpose, as well as characters not in this set, have to be encoded. URL encoding serves the purpose of replacing these non-conforming characters with a `%` symbol followed by two hexadecimal digits that represent the [ASCII code](http://www.asciitable.com/) of the character.

  Characters must be encoded if:

  1. They have no corresponding character within the standard [ASCII character set](http://www.asciitable.com/).
  2. The use of the character is unsafe because it may be misinterpreted, or even possibly modified by some systems. For example `%` is unsafe because it can be used for encoding other characters. Other unsafe characters include spaces, quotation marks, the `#` character, `<` and `>`, `{` and `}`, `[` and `]`, and `~`, among others.
  3. The character is reserved for special use within the URL scheme. Some characters are reserved for a special meaning; their presence in a URL serve a specific purpose. Characters such as `/`, `?`, `:`, `@`, and `&` are all reserved and must be encoded. For example `&` is reserved for use as a query string delimiter. `:` is also reserved to delimit host/port components and user/password.

  So what characters can be used safely within a URL? Only alphanumeric and special characters `$-_.+!'()",` and reserved characters when used for their reserved purposes can be used unencoded within a URL. As long as a character is not being used for its reserved purpose, it has to be encoded.

  * We need a safe way to represent these characters in a URL because using  them literally can "break" the URL, in that it will no longer be able to locate the resource in question.

    

4) **What is www in the URL?**

What you put into your browser to make an HTTP request.  The server sends back a raw response.  World Wide Web.  Arbitrary prefix 



5) **What is URI?**
   - A *URI* is an *identifier* for a *particular* resource within an information space.
   - A URL is a subset of URI, but the two terms are often used interchangeably.
     - A URL is a *type* of URI, which stands for Uniform Resource Identifier.
     - This refers to any kind of uniform string that identifies a particular resource, such as an ISBN for a publication.
     - A URL, unlike a URI, *must* include some piece of data that allows us to locate the resource in question, while a URI does not have this requirement.
     - URL refers to a specific kind of URI in which the formatting has  already been determined and it contains the location of a particular  resource on the web.
     - URL and URI are often used interchangeably but this is inaccurate.

A **Uniform Resource Identifier** (URI), is a string of characters which identifies a particular resource. It is part of a system by which resources should be uniformly **addressed** on the Web. On the [W3C website](https://www.w3.org/Addressing/), the purpose of a URI is described in the following way:

> The Web is an information space. Human beings have a lot of mental machinery for manipulating, imagining, and finding their way in spaces. URIs are the points in that space.

The terms URI and URL (Uniform Resource Locator) are often used interchangeably. We'll discuss the distinctions in a later assignment.  URI does not require location info 

URL is a subset of URI 



6) **What is the difference between scheme and protocol in URL?**

protocol all caps.. scheme lowercase... scheme doesn't specify which version just general protocol 