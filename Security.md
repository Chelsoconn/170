

1. **Describe some of the security threats and what can be done to minimize them?**

   * HTTP is *inherently insecure*. Security can be increased by using *HTTPS*, enforcing *Same-origin policy*, and using techniques to prevent *Session Hijacking* and *Cross-site Scripting*.
   * *HTTP Requests and Responses* are transferred in *plain text*; as such they are *essentially insecure*.
   * We can use the *Transport Layer Security* (TLS) Protocol to add security to HTTP communications.
   * *Packet sniffing, session hijacking, Cross Scripting* 

   THREAT - If a malicious hacker was attached to the same network, they could employ **packet sniffing** techniques to read the messages being sent back and forth. As we  learned previously, requests can contain the session id, which uniquely  identifies you to the server, so if someone else copied this session id, they could craft a request to the server and pose as your client, and  thereby automatically being logged in without even having access to your username or password.

   MINIMIZE THREAT - This is where Secure HTTP, or HTTPS, helps. A resource that's accessed by HTTPS will start with `https://` instead of `http://`, and usually be displayed with a lock icon in most browsers: With HTTPS every request/response is encrypted before being transported  on the network. This means if a malicious hacker sniffed out the HTTP  traffic, the information would be encrypted and useless.



​		THREAT - if an attacker gets a hold of the session id, both the attacker and the  user now share the same session and both can access the web application. In **session hijacking**, the user won't even know an attacker is accessing his or her session without ever even knowing the username or password

​	   MINIMIZE THREAT - 

		* One popular way of solving session hijacking is by resetting sessions.  With authentication systems, this means a successful login must render  an old session id invalid and create a new one. With this in place, on  the next request, the victim will be required to authenticate. At this  point, the altered session id will change, and the attacker will not be  able to have access. Most websites implement this technique by making  sure users authenticate when entering any potentially sensitive area,  such as charging a credit card or deleting the account.
	
	 * Same Origin Policy 
	
	 * Another useful solution is by setting an expiration time on sessions.  Sessions that do not expire give an attacker an infinite amount of time  to pose as the real user. Expiring sessions after, say 30 minutes, gives the attacker a far narrower window to access the app.
	  * Finally, as we have already covered, another approach is to use HTTPS across the entire app to minimize the chance that an attacker can get  to the session id.
	
	    

​		THREAT- **Cross-site scripting, or XSS**. This type of attack  happens when you allow users to input HTML or JavaScript that ends up  being displayed by the site directly.  Attackers can craft ingeniously malicious HTML and JavaScript and be  very destructive to both the server as well as future visitors of this  page. For example, an attacker can use JavaScript to grab the session id of every future visitor of this site and then come back and assume  their identity. It could happen silently without the victims ever  knowing about it. Note that the malicious code would bypass the  same-origin policy because the code lives on the site.

- Websites that allow some kind of input, such as allowing users to enter a comment that will be displayed, must protect against **cross site scripting** or **XSS**.
- This is when a malicious party uses site input fields to inject HTML or JavaScipt into the site directly.
- This can be prevented by performing *input sanitation*, such as getting rid of anything that might be problematic such as `<script>` tags.
- It's also possible to escape certain characters that indicate JavaScript or HTML code.
- Site's can also choose to only accept a safer form of input, such as Markdown.

MINIMIZE THREAT - 

* One way to prevent this kind of attack is by making sure to always  sanitize user input. Eliminate problematic input, such as <script> tags, or disallowing HTML and JavaScript input altogether in favor of a safer format, like Markdown.
* The second way to guard against XSS is to escape all user input data  when displaying it. If you do need to allow users to input HTML and  JavaScript, then when you print it out, make sure to escape it so that  the browser does not interpret it as code.

 



2. **What is the Same Origin Policy? How it is used to mitigate certain security threats?**

The same-origin policy is an important concept that permits unrestricted interaction between resources originating from the same origin, but  restricts certain interactions between resources originating from  different origins. What we mean by *origin* here is the combination of a url's scheme, hostname, and port. So `http://mysite.com/doc1` would be considered to have the same origin as `http://mysite.com/doc2`, but a different origin to `https://mysite.com/doc2` (different scheme), `http://mysite.com:4000/doc2` (different port), and `http://anothersite.com/doc2` (different host).

Same-origin policy doesn't restrict *all* cross-origin requests.  Requests such as linking, redirects, or form submissions to different  origins are typically allowed. Also typically allowed is the embedding  of resources from other origins, such as scripts, css stylesheets,  images and other media, fonts, and iframes. What *is* typically restricted are cross-origin requests where resources are being accessed programmatically using APIs such as `XMLHttpRequest` or `fetch` (the details of which are beyond the scope of this book).   



3. **TLS HANDSHAKE STEPS**
   - The *TLS Handshake* is the process by which a client and a server *exchange encryption keys*.
   - The *TLS Handshake* must be performed before secure data exchange can begin; it involves *several round-trips of latency* and therefore has an *impact on performance*.

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



4. **What is symmetric key encryption? What is it used for?**

- Symmetric key encryption is an encrypted communication system in  which both the sender and receiver posses a shared encryption key.

- The advantages to this are that it facilitates two-way  communication. Both parties can use the shared key to encode, send, and  decode messages to and from the other.

- This disadvantage is that a symmetric system relies on the fact that no one else has access to the key in order for it to remain secure.

- This means that it requires a secure way for both paries to exchange keys before symmetric encryption can be established, and this is  difficult to do on the web.

- For this reason, it is used in *conjunction* with asymmetric key encryption, which facilitates a secure exchange of a shared key

  

5. **What is asymmetric key encryption? What is it used for?**

- Asymmetric Key Encryption is an encrypted communications system which uses two distinct keys: a public key and a private key.
- The public key is used to encrypt and send a secure message to the  recipient, who holds the private key, which is used to decode the  encrypted message.
- This only facilitates one way communication, in which only the party who holds the private key can receive and decode secure communications.
- However, because it works only one way, we can se asymmetric key  encryption as a means for hosts to exchange symmetric encryption keys  during the TLS handshake process.



6. **Describe SSL/TLS encryption process.**
   * *TLS encryption* allows us to *encode messages* so that they can only be read by those with an authorized means of decoding the message
   * TLS encryption uses a combination of *Symmetric Key Encryption* and *Asymmetric Key Encryption*. Encryption of the initial key exchange is performed asymmetrically, and subsequent communications are symmetrically encrypted.

HTTPS sends messages through a cryptographic protocol called [TLS](http://en.wikipedia.org/wiki/Transport_Layer_Security) for encryption. Earlier versions of HTTPS used `SSL`or Secure Sockets Layer until `TLS` was developed. These cryptographic protocols use certificates to  communicate with remote servers and exchange security keys before data  encryption happens. You can inspect these certificates by clicking on  the padlock icon that appears before the `https://`:

To securely send messages via HTTP we want both the request *and* the response to be encrypted in a such a way that they can only be decrypted by the intended recipient. The most efficient way to do this is via symmetric key cryptography. If we want to use symmetric keys however, we also need a way to securely exchange the symmetric key.



7. **Describe the pros and cons of TLS Handshake**

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

8. **Why do we need digital TLS/SSL certificates?**
   * *TLS authentication* is a means of *verifying the identity* of a participant in a message exchange.
   * TLS Authentication is implemented through the use of *Digital Certificates*.
   * Certificates are *signed* by a *Certificate Authority*, and work on the basis of a *Chain of Trust* which leads to one of a small group of highly trusted *Root CAs*.
   * The server's certificate is *sent* during the *TLS Handshake* process.

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
     
       

9. **What is CA hierarchy and what is its role in providing secure message transfer?**

1. So who exactly are these Certificate Authorities, and why should we trust them? There are different 'levels' of CA. An 'Intermediate CA' can be any company or body authorised by a 'Root CA' to issue certificates on its behalf. A widely-used Intermediate CA is Let's Encrypt, who provide free, automated certificates.

2. Client software, such as browsers, store a list of these authorities along with their Root Certificates (which includes their public key). When receiving a certificate for checking, the browser can go up the chain to the Root Certificate stored in its list.

3. The purpose of this chain-like structure is the level of security it provides. The private keys of the Root CAs are kept behind many layers of security in order to be kept as inaccessible as possible. As such they don't issue end-user certificates, but leave that up to the Intermediate CAs. Additionally, if the private key of an Intermediate CA somehow became compromised, the root CA can revoke the certificate for Intermediate, therefore invalidating all of the certificates down the chain from it, and simply issue a new one.

   

10. **What is Cipher Suites and what do we need it for?**
    * A *cipher suite* is the *agreed set of algorithms* used by the client and server during the secure message exchange.

During the description of the TLS Handshake, we mentioned Cipher Suites a few times. So what exactly is a Cipher Suite?

A *cipher* is a cryptographic algorithm; in other words they are sets of steps for performing encryption, decryption, and other related tasks. A *cipher suite* is a suite, or set, of ciphers.

TLS uses different ciphers for different aspects of establishing and maintaining a secure connection. There are many algorithms which can be used for performing the key exchange process, as well as for carrying out authentication, symmetric key encryption, and checking message integrity.

The algorithms for performing each of these tasks, when combined, form the *cipher suite*. The suite to be used is agreed as part of the TLS Handshake. As part of the `ClientHello` message, the client sends a list of algorithms it supports for each required task, and the server chooses from these according to which algorithms it also supports.



11. **How does TLS add a security layer to HTTP?**

* TLS used to be SSL 

* 3 important security services that are provided by TLS:

* Each of these services are important in their own right, but when combined they provide for very secure message exchange over what is essentially an unsecure channel. Let's look a bit more closely at the nature of these services.

  1. *Encryption*-
     1. a process of encoding a message so that it can only be read by those with an authorized means of decoding the message
     2. See TLS Handshake 

  1. *Authentification*-
     1. a process to verify the identity of a particular party in the message exchange
     2. TLS Authentication is implemented through the use of *Digital Certificates*.
     3. Certificates are *signed* by a *Certificate Authority*, and work on the basis of a *Chain of Trust* which leads to one of a small group of highly trusted *Root CAs*

  1. *Integrity*-

     * *TLS Integrity* provides a means of *checking* whether a message has been *altered or interfered with* in transit.
     * TLS Integrity is implemented through the use of a *Message Authentication Code* (MAC).

     1. a process to detect whether a message has been interfered with or faked
        1. The main field that interests us in terms of providing message integrity is the `MAC` (*Message Authentication Code*- similar to checksum) field. Note that, though they use the same acronym, the Message Authentication Code is completely unrelated to the MAC Address (media access control address) discussed in an earlier lesson. The intention of the `MAC` field in a TLS record is to add a layer of security by providing a means of checking that the message hasn't been altered or tampered with in transit.
           1. The sender will create what's called a *digest* of the data payload. This is effectively a small amount of data derived from the actual data that will be sent in the message. The digest is created using a specific hashing algorithm combined with a pre-agreed hash value. This hashing algorithm to be used and hash value will have been agreed as part of the TLS Handshake process when the Cipher Suite is negotiated.
           2. The sender will then encrypt the data payload using the symmetric key (as described earlier in the Encryption section), encapsulate it into a TLS record, and pass this record down to the Transport layer to be sent to the other party.
           3. Upon receipt of the message, the receiver will decrypt the data payload using the symmetric key. The receiver will then also create a digest of the payload using the same algorithm and hash value. If the two digests match, this confirms the integrity of the message.



12. **What is server-side infrastructure? What are its basic components?**

A *web server* is typically a server that responds to requests for static assets: files, images, css, javascript, etc. These requests  don't require any data processing, so can be handled by a simple web  server.

An *application server*, on the other hand, is typically where application or business logic resides, and is where more complicated  requests are handled. This is where your server-side code lives when  deployed.

The application server will often consult a persistent *data store*, like a relational database, to retrieve or create data. Data stores can also be simple files, key/value stores, document stores and many other  variations, as long as it can save data in some format for later  retrieval and processing.



13. **What is a server? What is its role?**

Yet taken together as unified concept, the server-side infrastructure in its entirety is the "server" to the client. The word "server" is  severely overloaded, so it's important to keep in mind what exactly  we're talking about at every turn.



14. **What are optimizations that developers can do in order to improve performance and minimize latency?**

    - Cache 

    - reduce TCP connections 

    - Browser Optimization 

    - Compression techniques

    - DNS Optimizations 



15. **DTLS** 
    - DTLS stands for Datagram Transport Layer Security.
    - It is a separate protocol based on TLS that is used with network connections that utilize UDP instead of TCP
    - Because TLS is interlinked with TCP and the TCP handshake, separate  protocols are needed to meet the security requirements of UDP.