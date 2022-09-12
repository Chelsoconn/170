1. **What is a network?**

   1. 2 or more computers that are linked in order to share resources or exchange data.  They may be linked through cables, telephone lines, radio waves, satellites, or infrared light beams. 

      1. Local Area Network (LAN)- confined to a small area limited to a geographic region 	

         1. Computers connected to a network are called servers or workstations 

            1. Servers generally don't have a human user and provide services like printing, faxing, software hosting, file storage and sharing, complete access control for the networks resources, etc. Tend to be more powerful than workstations. A group of servers might be located in a secure area away from humans and only accessed through the network.
            2. Workstations generally have a human userwhich interacts with the network through them. Desktops for example.

            * May be connected through wires and cables (fastest) or wireless through **WAPS** or wireless access points. WAP devices provide a bridge between computers and networks.  Can connect hundreds or thousands of wireless users to a network.  The `hub` or `switch` is the network bridging device that the computers are linked to. Wireless local- area Network (WLAN) connect local computers wirelessly.

      2. Internetwork Communication - Switch connects to router, router from other LAN connects to that LAN's router to enable communication between networks.

      3. Network of networks- adds another group of routers in between communicating routers to direct network traffic.

      4. connect networks in larger geographic areas. Transoceanic cabling or satellite uplinks may be used to connect this type of global network. 

         1. Uses multiplexers, bridges, and routers to connect local and metropolitan networks to global communications networks like the Internet. 
         2. ex/ Wi-Fi

2. **What is the Internet?**

   1. A global network of billions of computers and other electonic devices.  You can access information by going online. 
   2. Relies on physical cables. Even wireless connections like Wi-Fi and 3G/4G rely on physical cables to access the internet. 
   3. When you visit a website, your computer sends a request over these wires to a  server. A server is where websites are stored, and works a lot like your computers hard drive. 

3. **Is the Internet the same thing as a network?**

   | S.NO | Network                                                      | Internet                                                     |
   | :--- | :----------------------------------------------------------- | :----------------------------------------------------------- |
   | 1.   | Network is defined as the group of two or more computer systems. | Whereas internet is the interrelationship of a few networks. |
   | 2.   | The coverage of network is limited in comparison of internet. | While it covers large geographical area.                     |
   | 3.   | It provides the link between many computers and network-enabled devices. | While it provide connection among many networks.             |
   | 4.   | The types of network are: LAN, MAN, WAN, CAN and HAM.        | Whereas the types of internet is world wide web.             |
   | 5.   | Through network, hundreds or a few thousands of computer system can linked simultaneously. | While through internet, millions of computer system can linked simultaneously. |
   | 6.   | It requires less number of hardware devices.                 | While it requires various hardware devices.                  |

4. **What is WEB (world wide web)**

   1. A collection of different websites you can access through the internet. 
   2. An information system enabling documents and other web resources to be accessed over the internet.

5. **What is a protocol?**

   ​			- IP = Internet Protocol

   1. a set of rules governing the exchange or transmission of data.
   2. Groups of protocols work in a layered system. Protocols at one layer provide services to the layer above.
   3. Data is encapsulated into a Protocol Data Unit, creating separation between protocols operating at different layers.
   4. The computers within a network may use vastly different software and hardware; however the use of protocols enables them to communicate with eachother regardless.
   5. ex/ Ethernet, HTTP, Wifi, Bluetooth, IP, DNS

6. **What is the role of protocols?**

   In order for computers to exchange information, there must be a preexisting agreement as to how the information will be structured and how each side will send and recieve it.  The main goal is to enable systems to communicate with each other.

7. **Why there are many different types of protocols?**

   - Different protocols weer developed to address different aspects of network communication ex communicating messages through talking TCP, UDP
     - Syntactical- order of words
     - Message transfer rules- who talks first 
   - Different protocols were developed to address the same aspect of network communication, but in a way different way or for a specific use-case ex/ talking to friends vs teachers vs presenter HTTP
     - Rules for hiearchical communication vs casual 

   Different needs:

   1) Need to move around and still stay connected- enhanced mobility
   2) Need for higher speeds of data exchange
   3) Need for secured exchange of info
   4) Need to reduce power consumption in data exchange
   5) Need to improve the usability of the connectors, in other words, make our life simpler. 

​		- Group protocols as functioning within layers of an overall system of communication. 

1. **What does it mean that a protocol is stateless?**

   A protocol in which each particular communication is handled as an independant event, unrelated to other similar communications.  

   1) ex/ HTTP, DNS

2. **Explain briefly what are OCI and TCP/IP (internet protocol suite) models? What is the purpose of having models like that?**

   1. Modularizing and structuring computer network communication models. 
      1. OSI 1-3 ~ IP 1 
      2. 4 ~ 2
      3. 5 ~ 3 
      4. 6-7 ~ 4

![Diagram comparing OSI model layers with TCP/IP layers](https://da77jsbdz4r05.cloudfront.net/images/ls170/layered-system-osi-tcp-ip-comparison.png)Each model takes a different approach. IP divides the laters in terms of the scope of communication within each layer (within local netwrok, between networks, etc.).  OSI divides the layers in terms of the function that each layer provides (physical addressing, logical addressing and routing, encryption, compression, etc. )	

- Useful for gaining a broad- brush view of how a system works as a whole, and for modularizing different levels of responsibility within that system. 
- Developing a clear idea of how a particular protocol works and how to use it at the implementation detail is more important than trying to strictly adhere to the model. 

3. **What is PDU? What is its role?**

Protocol Data Units (PDU) - an amount or block of data transferred over a network. Referred to as different names in different layers.

1. Consists of a header, a data payload, and in some cases a trailer/ footer
   1. Headers and footers provide protocol-specific metadata about the PDU.  Ex/ an Internet Protocol (IP) packet header would include fields for the Source IP Address and the Destination IP Address, which would be used to correctly route the packet.
   2. Data Payload- The data we want to transport over the network using a specific protocol at a particular network later

4. **What is Data Payload?**

The data we want to transport over the network using a specific protocol at a particular network later 

The key to the way encapsulation is implemented. The entire PDU from a protocol at one layer is set as the data payload for a protocol at the layer below. For example, a HTTP Request at the Application layer could be set as the payload for a TCP segment at the transport layer.



![Diagram demonstrating concept of encapsulation i the context of PDUs at different network layers ](https://da77jsbdz4r05.cloudfront.net/images/ls170/layered-system-encapsulation.png)



Separation created between protocols at different layers. A protocol at one layer doesn't need to know anything about how a protocol at another layer is implemented in order for those protocols to interact. 

1. **Explain How lower-level protocols work in general?**

   It can independently complete its specific communication task without information from other layers. It creates a system whereby a lower layer effectively provides a 'service' to the layer above it. In other words, a TCP segment isn't really concerned whether its data payload is an HTTP request, an SMTP command, or some other sort of Application layer data. It just knows it needs to encapsulate *some data* from the layer above and provide the result of this encapsulation to the layer below. This separation of layers provides a certain level of abstraction, which allows us to use different protocols at a certain layer without having to worry about the layers below. This is especially apparent at the Application layer, where many different protocols are used depending on the application and use case. For example, an email client would use SMTP, and web browser HTTP, and a file transfer program FTP, but all three of these programs could use TCP at the Transport layer to transfer the application layer data.

2. **What is encapsulation in the context of networking?**

   1. Hiding data from one layer by encapsulating it within a data unit of the layer below. 
      1. Protocol Data Units (PDU) - an amount or block of data transferred over a network. Referred to as different names in different layers.
         1. Consists of a header, a data payload, and in some cases a trailer/ footer
            1. Headers and footers provide protocol-specific metadata about the PDU.  Ex/ an Internet Protocol (IP) packet header would include fields for the Source IP Address and the Destination IP Address, which would be used to correctly route the packet.
            2. Data Payload- The data we want to transport over the network using a specific protocol at a particular network later 

![Simple image of a PDU consisting of header and payload](https://da77jsbdz4r05.cloudfront.net/images/ls170/layered-system-pdu.png)

1. **What are the characteristics of a physical network?**

   1. Latency
   2. Bandwidth

2. **How can we as developers deals with the limitations of physical network?**

   As developers and software engineers, there's really not a lot we can do about the limitations of the physical network itself. If we want to improve the performance of the applications we build, then 

   *our influence is limited to the implementation of the application in terms of how we use the higher-level protocols*.

    As we'll see later in the course, however, an understanding of these physical limitations can impact the way we think about those higher-level protocols, and therefore the decisions we make about how we use them within our applications.

3. **What is Latency?**

   1. Measure of the time it takes for some data to get from one point in a network to another point in a network.
   2. measure of delay.  
   3. There are different types of delay that fo together to determine the overall latency of a network connection. All these combined are the total latency in milliseconds (ml).
      1. Propagation delay- amount of time for a message to travel from the sender to the reciever 
         1. Ratio between distance and speed.
      2. Transmission delay- amount of time it takes to push data onto the "link"= Each of the elements in a network can be thought of as an induvidual link which are all interconnected by switches, routers, and other network devices
         1. Explore `traceroute` - 
            1. a utility for displaying the route and latency of the path across a network. Running the command should return a list of hops taken for the test data to get from your PC or laptop to the Google server. The values indicated here are the Round Trip Time for each hop.
      3. Processing delay- Data taveling across a physical network doesn't directly cross one link to another, but is processed in various ways 
      4. Queuing Delay- Network devices such as routers can only process a certain amount of data at one time before it needs to queue or buffer the data. The amount of time in 'traffic' is the queuing delay.
   4. Last-mile Latency- A lot of the delays can take place within the parts of the network which are closest to the end points. Relates to the delays involoved in getting the network signal from your ISP's network to your home or office network.
   5. Round-trip Time(RTT)- A latency calculation often used in networking is Round Trip Time.  This is the length of time for a seignal to be sent, added to the length of time for an acknowledgement or response to be recieved. 

4. **What is** **Bandwidth?**

   1. The amount of data that can be sent in a particular unit of time (typically a second)
   2. Increasing badwidth only lets you increase the amount of data sent, not the speed, or latency.
   3. Varies across the network and isnt at a constant level between the start point and the end point of our data's journey. The capacity of the core network is much higher than the part of the network infrastructure that ultimately connects to your home or office building. 
   4. The bandwidth that a connection receives is the lowest amount at a particular point in the overall connection. A point at which bandwidth changes from relatively high to relatively low is generally referred to as a bandwidth bottleneck.
   5. Low bandwidth can be an issue when dealing with large amounts of data. As we'll see later in the course, however, in many situations latency can be a much more serious limitation on the performance of a networked application.

5. **What are** **Network 'Hops'?**

   This is related to Last Mile latency seen in `Latency`.  The hops within the core part of the network signal from your ISP's network to your home or office network, processing, or queuing.  At the network edge, there are more frequent and shorter hops as the data is directed down the network hierarchy to the appropriate sub-network.  You can think of the network edge as the entry point into a network like a home or corporate LAN.

   - The journey of a piece of data on a network isnt direct from a start point to a finsh but is a journey of "hops" between nodes on the network. Think of nodes as routers that process the data and forward it to the next node on the path.
     - Run `traceroute google.com` in terminal
       - Utility for displaying the route and latency of a path across a network. Running the command should return a list of hops taken for the test data to get from your PC or laptop to the Google server. The values indicated here are the Round-Trip Time (RTT) for each hop.

   

   **What is a switch and what is it used for?**

6. **What is a hub and what is it used for?**

7. **What is a modem and what it is used for?**

8. **What is a router and what is it used for?**

9. **What is the difference between a switch, hub, modem, and router?**

10. **How does the Internet works?**

11. **What is a MAC address and what is its role in network communication?**

12. **Give an overview of the Link/Data Layer**

    In the OSI model, the Data Link Layer is Layer 2 and comes in between the Physical Layer(1) and the Network Layer(3).  In the Internet Protocol Suite, the Link Layer is 1.	

     * The layer is an interface between the workings of the physical network and the more logical layers above.

     * The most commonly used protocol at this later is the `Ethernet` protocol

       * Ethernet cables connect devices on the network such as computers, switches, and routers.

       * The technical specification of these cables is governed by the same [IEEE standards](https://standards.ieee.org/standard/802_3-2018.html) that include the Ethernet communication protocols that operate at this layer of the network.

         Two of the most important aspects of Ethernet are *framing and addressing.*

13. **What is included in an Ethernet frame?**

    ​		- DATA PAYLOAD field is used as an encapsulation mechanism for the layer 

![Graphic showing structure of an Ethernet Frame](https://da77jsbdz4r05.cloudfront.net/images/ls170/data-link-layer-frame-structure.png)

Ethernet frames are a Protocol Data Unit, and encapsulate data from the Internet/ Netwrok layer above. This is the lowest level of encapsulation.Ethernet Frame adds logical structure to the physical binary data. Data in this frame are still in bits, but the structure defines shich bits are actually the data payload, which are the metadata to be used in the process of transporting the frame. An ethernet- compliant network device is able to identify the different parts of the frame due to the fact that different 'fields' of data have specific lengths in bytes and appear in a set order.

- **Preamble and SFD:** The Preamble and Start of Frame Delimiter (SFD/ SOF) generally aren't considered part of the actual frame but are sent just prior to the frame as a synchronization measure which notifies the receiving device to expect frame data and then identify the start point of that data. The preamble is seven bytes (56 bits) long and the SFD is one byte (eight bits). Both use a repeated pattern that can be recognised by the receiving device, which then knows that the data following after is the frame data.
- **Source and Destination MAC address:** The next two fields, each six bytes (48 bits) long, are the source and destination MAC addresses. The source address is the address of the device which created the frame (as we'll see later on in this assignment, this can change at various points along the data's journey). The destination MAC address is the address of the device for which the data is ultimately intended. MAC Addresses are a key part of the Ethernet protocol; we'll look at them in more detail shortly.
- **Length:** the next field is two bytes (16 bits) in length. It is used to indicate the size of the Data Payload.
- **DSAP, SSAP, Control:** The next three fields are all one byte (8 bits) in length. The DSAP and SSAP fields identify the Network Protocol used for the Data Payload. The Control field provides information about the specific communication mode for the frame, which helps facilitate flow control.
- **Data Payload:** the data payload field can be between 42 and 1497 bytes in length. It contains the data for the entire Protocol Data Unit (PDU) from the layer above, an IP Packet for example.
- **Frame Check Sequence (FCS):** The final four bytes (32 bits) of an Ethernet Frame is the Frame Check Sequence. This is a checksum generated by the device which creates the frame. It is calculated from the frame data using an algorithm such as a cyclic redundancy check. The receiving device uses the same algorithm to generate a FCS and then compares this to the FCS in the sent frame. If the two don't match, then the frame is dropped. Ethernet doesn't implement any kind of retransmission functionality for dropped frames; it is the responsibility of higher level protocols to manage retransmission of lost data if this is a requirement of the protocol.

1. **Give an overview of the Internet/Network Layer and it's role.**
2. **What is IP?**
3. **What is IP address?**
4. **What are the components of IP addresses?**
5. **What is a packet in computer networking?**
6. **Why do we need both MAC addresses and IP addresses?**
7. **What is DNS and how does it work?**
8. **How do port numbers and IP addresses work together?**
9. **What is a checksum and what is it used for? How is it used?**
10. **Give an overview of the Transport Layer.**
11. **What are the fundamental elements of reliable protocol?**
12. **What is pipe-lining protocols? What are the benefits of it?**
13. **What is a network port?**
14. **What is a port number?**
15. **What is a network socket?**
16. **Is TCP connectionless? Why?**
17. **How do sockets on the implementation level relate to the idea of protocols being connectionless or connection-oriented?**
18. **What are sockets on implementation and on a theoretical level?**
19. **What does it mean that the protocol is connection-oriented?**
20. **What is a three-way handshake? What is it used for?**
21. **What are the advantages and disadvantages of a Three-way handshake?**
22. **What are multiplexing and demultiplexing?**
23. **How does TCP facilitate efficient data transfer?**
24. **What is flow control? How does it work and why do we need it?**
25. **How TCP prevents from receiver's buffer to get overloaded with data?**
26. **What is congestion avoidance?**
27. **What is network congestion?**
28. **How do transport layer protocols enable communication between processes?**
29. **Compare UDP and TCP. What are similarities, what are differences? What are pros and cons of using each one?**
30. **What does it mean that network reliability is engineered?**
31. **Give an overview of the Application Layer.**
32. **What is HTML?**
33. **What is a URL and what components does it have?**
34. **What is a Query string? What it is used for?**
35. **What URL encoding is and when it might be used for?**
36. **Which characters have to be encoded in the URL? Why?**
37. **What is www in the URL?**
38. **What is URI?**
39. **What is the difference between scheme and protocol in URL?**
40. **What is HTTP?**
41. **What is the role of HTTP?**
42. **Explain the client-server model of web interactions, and the role of HTTP as a protocol within that model**
43. **What are HTTP requests and responses? What are the components of each?**
44. **Describe the HTTP request/response cycle.**
45. **What is a** s**tate in the context of the 'web'?**
46. **What is** s**tatelessness?**
47. **What is a stateful Web Application?**
48. **How can we mimic a stateful application?**
49. **What is the difference between stateful and stateless applications?**
50. **What does it mean that HTTP is a 'stateless protocol?**
51. **Why HTTP makes it difficult to build a stateful application?**
52. **How the idea that HTTP is a stateless protocol makes the web difficult to secure?**
53. **What is a `GET` request and how does it work?**
54. **How is `GET` request initiated?**
55. **What is the HTTP response body and what do we use it for?**
56. **What are the obligatory components of HTTP requests?**
57. **What are the obligatory components of HTTP response?**
58. **Which HTTP method would you use to send sensitive information to a server? Why?**
59. **Compare `GET` and `POST` methods.**
60. **Describe how would you send a `GET` request to a server and what would happen at each stage.**
61. **Describe how would you send `POST` requests to a server and what is happening at each stage.**
62. **What is a status code? What are some of the status codes types? What is the purpose of status codes?**
63. **Imagine you are using an HTTP tool and you received a status code `302`. What does this status code mean and what happens if you receive a status code like that?**
64. **How do modern web applications 'remember' state for each client?**
65. **What role does AJAX play in displaying dynamic content in web applications?**
66. **Describe some of the security threats and what can be done to minimize them?**
67. **What is the Same Origin Policy? How it is used to mitigate certain security threats?**
68. **What determines whether a request should use `GET` or `POST` as its HTTP method?**
69. **What is the relationship between a scheme and a protocol in the context of a URL?**
70. **In what ways can we pass information to the application server via the URL?**
71. **How insecure HTTP message transfer looks like?**
72. **What services does HTTP provide and what are the particular problems each of them aims to address?**
73. **What is TLS Handshake?**
74. **What is symmetric key encryption? What is it used for?**
75. **What is asymmetric key encryption? What is it used for?**
76. **Describe SSL/TLS encryption process.**
77. **Describe the pros and cons of TLS Handshake**
78. **Why do we need digital TLS/SSL certificates?**
79. **What is it CA hierarchy and what is its role in providing secure message transfer?**
80. **What is Cipher Suites and what do we need it for?**
81. **How does TLS add a security layer to HTTP?**
82. **Compare HTTP and HTTPS.**
83. **Does HTTPS use other protocols?**
84. **How do you know a website uses HTTPS?**
85. **Give examples of some protocols that would be used when a user interacts with a banking website. What would be the role of those protocols?**
86. **What is server-side infrastructure? What are its basic components?**
87. **What is a server? What is its role?**
88. **What are optimizations that developers can do in order to improve performance and minimize latency?**



-try

HTTP and GUI need to be installed locally. Otherwise use AWS Cloud9