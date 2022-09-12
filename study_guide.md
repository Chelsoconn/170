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

   ​	A switch is a piece of hardware to which you connext devices to create a network.  Unlike a hub, a switch uses the destination address in order to direct a frame only to the device it is intended for. A switch keeps and updates a record of MAC addresses of the devices connected to it on a MAC Address Table, and assiciates each address with the Ethernet port to which the device is connected on the switch.

| Switch Port | MAC Address       |
| :---------- | :---------------- |
| 1           | 00:40:96:9d:68:0a |
| 2           | 00:A0:C9:14:C8:29 |
| 3           | D8:D3:85:EB:12:E3 |
| 4           | 00:1B:44:11:3A:B7 |



1. **What is a hub and what is it used for?**

   A basic piece of network hardware that replicates a message and forwards it to all the devices on the network.

   This is fine if you want to send a particular message and forward it to the entire network, but usually you want to specify which specific device the message is intended for.

2. **What is a modem and what it is used for?**

3. **What is a router and what is it used for?**

   1. All routers on a network store a local routing table.  When an IP packet is recieved by a router, the router examines the destination IP address and matches it with a list of network addresses in its routing table.  These network addresses define a range of addresses within a particular subnet.  The matching network address will determine where in the network hierachy the subnet exists.  This will then be used to select the best route for the IP packet to travel.

4. **How does the Internet works?**

   - The internet is a vast *network of networks*. It is comprised of both the *network infrastructure* itself (devices, routers, switches, cables, etc) and the *protocols* that enable that infrastructure to function.
   - Protocols are *systems of rules*. Network protocols are systems of rules governing the exchange or transmission of data over a network.

5. **What is a MAC address and what is its role in network communication?**

   MAC = Media Access Control Device 

   Every Network-Enabled-Device has a NIC (network interface card) and is assigned a specific MAC address (physical or burned in address) when manufactured.

   Ex/ `00:40:96:9d:68:0a`

   - In our hub scenario, each receiving device would check its MAC Address against the Destination MAC Address in the Frame to check if it was the intended recipient. If it wasn't, then it would just ignore the frame. Hubs are inefficient bc you're sending the frame to every computer, so switch's are used.
   - We cant scale the use of MAC addresses to a huge scale:
     - They are physical rather than logical. Each MAC Address is tied (burned in) to a specific physical device
     - They are flat rather than hierarchical. The entire address is a single sequence of values and can't be broken down into sub-divisions.
     - THE IP is the set of rules that makes this scalable 

   

6. **Give an overview of the Link/Data Layer**

   In the OSI model, the Data Link Layer is Layer 2 and comes in between the Physical Layer(1) and the Network Layer(3).  In the Internet Protocol Suite, the Link Layer is 1.	

    * The layer is an interface between the workings of the physical network and the more logical layers above.

    * The most commonly used protocol at this later is the `Ethernet` protocol

      * Ethernet cables connect devices on the network such as computers, switches, and routers.

      * The technical specification of these cables is governed by the same [IEEE standards](https://standards.ieee.org/standard/802_3-2018.html) that include the Ethernet communication protocols that operate at this layer of the network.

        Two of the most important aspects of Ethernet are `*framing and addressing.*`

7. **What is included in an Ethernet frame?**

   		- DATA PAYLOAD field is used as an encapsulation mechanism for the layer 
   		- An Ethernet Frame is structured data. 
   		- Important parts are Destination MAC address, Source MAC address and Data Payload 
   		- Interframe Gaps (IFG)- brief pause between transmission of each frame, which permits the reciever to prepare for the next frame. Contributes to the latency Transmission Delay
   		- IEEE 802.3 Ethernet Standard- describes structure of frame 
   		- The main elements to focus on are the Data Payload field being used as an encapsulation mechanism for the layer above, and the MAC Address fields being used to direct the frame between network devices. These particular fields exist across all the different Ethernet standards.

![Graphic showing structure of an Ethernet Frame](https://da77jsbdz4r05.cloudfront.net/images/ls170/data-link-layer-frame-structure.png)

Ethernet frames are a Protocol Data Unit, and encapsulate data from the Internet/ Network layer above. This is the lowest level of encapsulation.Ethernet Frame adds logical structure to the physical binary data. Data in this frame are still in bits, but the structure defines shich bits are actually the data payload, which are the metadata to be used in the process of transporting the frame. An ethernet- compliant network device is able to identify the different parts of the frame due to the fact that different 'fields' of data have specific lengths in bytes and appear in a set order.

- **Preamble and SFD:** The Preamble and Start of Frame Delimiter (SFD/ SOF) generally aren't considered part of the actual frame but are sent just prior to the frame as a synchronization measure which notifies the receiving device to expect frame data and then identify the start point of that data. The preamble is seven bytes (56 bits) long and the SFD is one byte (eight bits). Both use a repeated pattern that can be recognised by the receiving device, which then knows that the data following after is the frame data.
- **Source and Destination MAC address:** The next two fields, each six bytes (48 bits) long, are the source and destination MAC addresses. The source address is the address of the device which created the frame (as we'll see later on in this assignment, this can change at various points along the data's journey). The destination MAC address is the address of the device for which the data is ultimately intended. MAC Addresses are a key part of the Ethernet protocol; we'll look at them in more detail shortly.
- **Length:** the next field is two bytes (16 bits) in length. It is used to indicate the size of the Data Payload.
- **DSAP, SSAP, Control:** The next three fields are all one byte (8 bits) in length. The DSAP and SSAP fields identify the Network Protocol used for the Data Payload. The Control field provides information about the specific communication mode for the frame, which helps facilitate flow control.
- **Data Payload:** the data payload field can be between 42 and 1497 bytes in length. It contains the data for the entire Protocol Data Unit (PDU) from the layer above, an IP Packet for example.
- **Frame Check Sequence (FCS):** The final four bytes (32 bits) of an Ethernet Frame is the Frame Check Sequence. This is a checksum generated by the device which creates the frame. It is calculated from the frame data using an algorithm such as a cyclic redundancy check. The receiving device uses the same algorithm to generate a FCS and then compares this to the FCS in the sent frame. If the two don't match, then the frame is dropped. Ethernet doesn't implement any kind of retransmission functionality for dropped frames; it is the responsibility of higher level protocols to manage retransmission of lost data if this is a requirement of the protocol.

1. **Give an overview of the Internet/Network Layer and it's role.**

   OSI- network layer 3 between Data Link and Transport 

   TCP/ IP- Internet later is 2 between Link and Transport- PREDOMINANTLY used 

   - primary function of protocols at this layer is to facilitate communication between hosts (e.g. computers) on different networks.- internetwork comm.

2. **What is IP?**

   Internet Protocol is the predominant protocol used for Internet/Network Layer.

   Two versions - 

    	1) *IPv4*, IPv6
    	 	1) Routing capabilities via IP addressing 
    	 	2) Encapsulation of data into packets
    	 	3) PDU within the IP protocol is a `packet`- comprised of a data payload and a header. Data payload is the PDU from Transport. Data is in bits like in Ethernet frame. Logical separation is determined by the set size of each field in bits and the order within the packet. 

We won't describe every field in the header, but some of the more important ones to be aware of are:

- **Version:** this indicates the version of the Internet Protocol used, e.g. IPv4

- **ID, Flags, Fragment Offset:** these fields are related to fragmentation. If the Transport layer PDU is too large to be sent as a single packet, it can be fragmented, sent as multiple packets, and then reassembled by the recipient.

- **TTL:** every packet has a Time to Live (TTL) value. This is to ensure that any packets which don't reach their destination for some reason aren't left to endlessly bounce around the network. The TTL indicates the maximum number of network 'hops' a packet can take before being dropped. At each hop, the router which processes and forwards the packet will decrement the TTL value by one.

- **Protocol:** this indicates the protocol used for the Data Payload, e.g. TCP, UDP, etc.

- **Checksum:** this is an error checking value generated via an algorithm. The destination device generates a value using the same algorithm and if it doesn't match, it drops the packet. IP doesn't manage retransmission of dropped packets. This is left to the layers above to implement.

- **Source Address:** the 32-bit IP address of the source (sender) of the packet

- **Destination Address:** the 32-bit IP address of the destination (intended recipient) of the packet

  

1. **What is IP address?**

   1. Unlike MAC addresses, IP addresses are logical- they are not tied to a specific device, but can be assigned as required to devices as they join a network.
   2. The IP address that the device is assigned must fall within a range of addresses available to the local network that the device is connected to.
      1. Range is defined by a network hierarchy- the overall network is split into logical subnetworks, with each defined by the range of IP addresses available to it 

2. **What are the components of IP addresses?**

   32 bits adn divided into 4 sections of eight bits each.  

3. **Why do we need both MAC addresses and IP addresses?**

   MAC addresses - Who you are (physical)- Who lives there?- DATA LINK 

   IP- Where you are (logical)- like a home address- changes each time- NETWORK

   Need both working in different ways.

   	1) MAC used to identify a device while IP is used to locate a device
   	1) MAC is resposible for local identification, IP for global

   The routers send out ARP broadcast to get MAC address of next router. IP address lets you know final address.

4. **What is DNS and how does it work?**

   1. DOMAIN SPECIFIC

5. **How do port numbers and IP addresses work together?**

6. **What is a checksum and what is it used for? How is it used?**

   An error checking value generated via an algorithm. The destination device generates a value using the same algorithm and if it doesn't match, it drops the packet. IP doesn't manage retransmission of dropped packets. This is left to the layers above to implement.



***LESSON 1 SUMMARY***

#  Summary

- The internet is a vast *network of networks*. It is comprised of both the *network infrastructure* itself (devices, routers, switches, cables, etc) and the *protocols* that enable that infrastructure to function.
- Protocols are *systems of rules*. Network protocols are systems of rules governing the exchange or transmission of data over a network.
- Different types of protocol are concerned with different aspects of network communication. It can be useful to think of these different protocols as operating at particular 'layers' of the network.
- *Encapsulation* is a means by which protocols at different network layers can work together.
- Encapsulation is implemented through the use of *Protocol Data Units* (PDUs). The PDU of a protocol at one layer, becomes the data payload of the PDU of a protocol at a lower layer.
- The *physical network* is the tangible infrastructure that transmits the electrical signals, light, and radio waves which carry network communications.
- *Latency is a measure of delay*. It indicates the amount of time it takes for data to travel from one point to another.
- *Bandwidth is a measure of capacity*. It indicates the amount of data that can be transmitted in a set period of time.
- *Ethernet* is a set of standards and protocols that enables *communication between devices on a local network*.
- Ethernet uses a Protocol Data Unit called a Frame.
- Ethernet uses *MAC addressing* to identify devices connected to the local network.
- The *Internet Protocol* (IP) is the predominant protocol used for *inter-network communication*.
- There are two versions of IP currently in use: IPv4 and IPv6.
- The *Internet Protocol* uses a system of addressing (IP Addressing) to *direct data between one device and another across networks*.
- IP uses a Protocol Data Unit called a Packet.



1. **Give an overview of the Transport Layer.**

   running multiple apps at once- We can perhaps think of these different applications or processes as distinct *channels* for communication on a host machine.

   So, although we have multiple communication channels *on* a host, with IP addresses we only have a single channel *between*hosts. What we need is a way to transmit these multiple data inputs over this single host-to-host channel and then somehow separate them out at the other end.

   Getting data from Application layer and breaking it into packets, and attaching meta-info (source dest. ports) 

   Destination port numbers are included in the PDU (Protocol Data Unit) for the Transport Layer.  The name, and exact structure, of these PDUs varies according to the Transport Protocol used, but what they have in common is that they include these two pieces of information.

![Simple graphic of a transport layer PDU showing source and destination ports](https://da77jsbdz4r05.cloudfront.net/images/ls170/transport-comms-between-processes-simple-pdu.png)

* Data from the application layer is encapsulated as the data payload in this PDU, and the source and destination port numbers within the PDU can be used to direct that data to specfic processes on a host. The entire PDU is then encapsulated as the data payload in an IP packet.
*  The IP address and the port number *together* are what enables end-to-end communication between specific applications on different machines. The combination of IP address and port number information can be thought of as defining a *communication end-point*. This communication end-point is generally referred to as a *socket*.



1. **What are the fundamental elements of reliable protocol?**

2. **What is pipe-lining protocols? What are the benefits of it?**

3. **What is a network port?**

   A port is an identifier for a specific process running on a host. This identifier is an integer in the range 0-65535. 

   A port is NOT a physical connection. Its a logical connection thats used by programs and services to exchange info.

   Its specifically determines which program or service on a computer or server that is going to be used.

   Always associated with an IP address- work together to exchange data on a network 

4. **What is a port number?**

   - Unique number that identifies them. 

   1. 0-1023 are well-known ports. These are assigned to processes that provide commonly used network services. For example HTTP is port 80, FTP is port 20 and 21, SMTP is port 25, and so on.
   2. 1024-49151 are registered ports. They are assigned as requested by private entities. For example, companies such as Microsoft, IBM, and Cisco have ports assigned that they use to provide specific services. On some operating systems, ports in this range are also used for allocation as *ephemeral ports* on the client side.
   3. 49152-65535 are dynamic ports (sometimes known as private ports). Ports in this range cannot be registered for a specific use. They can be used for customized services or for allocation as *ephemeral ports*.

5. **What is a network socket?**

   The IP address and the port number together are what enables end-to-end communication between specific applications on different machines.  The combination of IP address and port number info can be thought of as defining a `communication end-point`- generally referred to as the socket. Ex/ 216.3.128.12:8080

   - An abstraction for an endpoint used for inter-process communication
   - At an implementation level, it can be used to refer to different specific things:
     - UNIX socket: a mechanism for communication between local processes running on the same machine.
     - Internet sockets (such as a TCP/IP socket): a mechanism for inter-process communication between networked processes (usually on different machines).
     - There *is* a distinction between the concept of a network socket and its implementation in code.

6. **Is TCP connectionless? Why?**

   Transmission Control Protocol- Connection Oritented Protocol

   Establishes connection with server after the data is broken down into packets from the application layer.

   - Check connections by running `netstat -ap TCP` in terminal

7. **How do sockets on the implementation level relate to the idea of protocols being connectionless or connection-oriented?**

8. **What are sockets on implementation and on a theoretical level?**

9. **What does it mean that the protocol is connection-oriented?**

10. **What is a three-way handshake? What is it used for?**

    In the TCP (Transmission Control Protocol) protocol. Establishing a connection with the server. 

    1) Client sends SYN (synchronized) packet to the server - 'Hey server I want to establish a connection with you'. 
    2) Server recieves it and sends back SYN ACK (synchronized acknowledgement)- "hey I'm ready to accept the connection"
    3) Client recieves and sends back ACK (acknowledgement)- connection established! 
       1) Packet Transmission can start

11. **What are the advantages and disadvantages of a Three-way handshake?**

12. **What are multiplexing and demultiplexing?**

    In the context of a communication network, this idea of transmitting multiple signals over a single channel is known as multiplexing, with demultiplexing being the reverse process. Takes place through the use of network ports.

13. **How does TCP facilitate efficient data transfer?**

14. **What is flow control? How does it work and why do we need it?**

15. **How TCP prevents from receiver's buffer to get overloaded with data?**

16. **What is congestion avoidance?**

17. **What is network congestion?**

18. **How do transport layer protocols enable communication between processes?**

19. **Compare UDP and TCP. What are similarities, what are differences? What are pros and cons of using each one?**

20. **What does it mean that network reliability is engineered?**

21. **Give an overview of the Application Layer.**

22. **What is HTML?**

23. **What is a URL and what components does it have?**

24. **What is a Query string? What it is used for?**

25. **What URL encoding is and when it might be used for?**

26. **Which characters have to be encoded in the URL? Why?**

27. **What is www in the URL?**

28. **What is URI?**

29. **What is the difference between scheme and protocol in URL?**

30. **What is HTTP?**

31. **What is the role of HTTP?**

32. **Explain the client-server model of web interactions, and the role of HTTP as a protocol within that model**

33. **What are HTTP requests and responses? What are the components of each?**

34. **Describe the HTTP request/response cycle.**

35. **What is a** s**tate in the context of the 'web'?**

36. **What is** s**tatelessness?**

37. **What is a stateful Web Application?**

38. **How can we mimic a stateful application?**

39. **What is the difference between stateful and stateless applications?**

40. **What does it mean that HTTP is a 'stateless protocol?**

41. **Why HTTP makes it difficult to build a stateful application?**

42. **How the idea that HTTP is a stateless protocol makes the web difficult to secure?**

43. **What is a `GET` request and how does it work?**

44. **How is `GET` request initiated?**

45. **What is the HTTP response body and what do we use it for?**

46. **What are the obligatory components of HTTP requests?**

47. **What are the obligatory components of HTTP response?**

48. **Which HTTP method would you use to send sensitive information to a server? Why?**

49. **Compare `GET` and `POST` methods.**

50. **Describe how would you send a `GET` request to a server and what would happen at each stage.**

51. **Describe how would you send `POST` requests to a server and what is happening at each stage.**

52. **What is a status code? What are some of the status codes types? What is the purpose of status codes?**

53. **Imagine you are using an HTTP tool and you received a status code `302`. What does this status code mean and what happens if you receive a status code like that?**

54. **How do modern web applications 'remember' state for each client?**

55. **What role does AJAX play in displaying dynamic content in web applications?**

56. **Describe some of the security threats and what can be done to minimize them?**

57. **What is the Same Origin Policy? How it is used to mitigate certain security threats?**

58. **What determines whether a request should use `GET` or `POST` as its HTTP method?**

59. **What is the relationship between a scheme and a protocol in the context of a URL?**

60. **In what ways can we pass information to the application server via the URL?**

61. **How insecure HTTP message transfer looks like?**

62. **What services does HTTP provide and what are the particular problems each of them aims to address?**

63. **What is TLS Handshake?**

64. **What is symmetric key encryption? What is it used for?**

65. **What is asymmetric key encryption? What is it used for?**

66. **Describe SSL/TLS encryption process.**

67. **Describe the pros and cons of TLS Handshake**

68. **Why do we need digital TLS/SSL certificates?**

69. **What is it CA hierarchy and what is its role in providing secure message transfer?**

70. **What is Cipher Suites and what do we need it for?**

71. **How does TLS add a security layer to HTTP?**

72. **Compare HTTP and HTTPS.**

73. **Does HTTPS use other protocols?**

74. **How do you know a website uses HTTPS?**

75. **Give examples of some protocols that would be used when a user interacts with a banking website. What would be the role of those protocols?**

76. **What is server-side infrastructure? What are its basic components?**

77. **What is a server? What is its role?**

78. **What are optimizations that developers can do in order to improve performance and minimize latency?**



HTTP and GUI need to be installed locally. Otherwise use AWS Cloud9