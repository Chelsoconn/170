1. **Give an overview of the Transport Layer.**

   - The underlying network is *inherently unreliable* (IP- Internet). If we want reliable data transport we need to implement a system of rules to enable it.
   - TCP provides reliability through *message acknowledgment* and *retransmission*, and *in-order delivery*.
   - TCP also provides *Flow Control* and *Congestion Avoidance*

   Running multiple apps at once- We can perhaps think of these different applications or processes as distinct *channels* for communication on a host machine. (DIFFERENT PORTS)

   So, although we have multiple communication channels *on* a host, with IP addresses we only have a single channel *between* hosts. What we need is a way to transmit these multiple data inputs over this single host-to-host channel and then somehow separate them out at the other end.

   Getting data from the Application layer and breaking it into packets, and attaching meta-info (source dest. ports) 

   Destination port numbers are included in the PDU (Protocol Data Unit) for the Transport Layer.  The name and exact structure, of these PDUs, vary according to the Transport Protocol used, but what they have in common is that they include these two pieces of information.

![Simple graphic of a transport layer PDU showing source and destination ports](https://da77jsbdz4r05.cloudfront.net/images/ls170/transport-comms-between-processes-simple-pdu.png)

* Data from the application layer is encapsulated as the data payload in this PDU, and the source and destination port numbers within the PDU can be used to direct that data to specific processes on a host. The entire PDU is then encapsulated as the data payload in an IP packet.

* The IP address and the port number *together* are what enable end-to-end communication between specific applications on different machines. The combination of IP address and port number information can be thought of as defining a *communication end-point*. This communication end-point is generally referred to as a *socket*.

* **TCP protocol** - 

  * The Transmission Control Protocol (TCP) is one of the cornerstones of the Internet. One of the key characteristics of this protocol is the fact that it provides reliable data transfer. In fact, reliability is listed as a key element of TCP operation as defined in [RFC793](https://www.ietf.org/rfc/rfc793.txt).

  > The TCP must recover from data that is damaged, lost, duplicated, or delivered out of order by the internet communication system.

  - **What TCP essentially provides is the abstraction of reliable network communication on top of an unreliable channel.  The Transport layer is the level of the networking model that is concerned with providing end-to-end communications between specific processes.** What this abstraction does is hide much of the complexity of reliable network communication from the application layer: data integrity, de-duplication, in-order delivery, and retransmission of lost data.
  - These protocols are able to direct data transfer to a specific process or application on a host because the facilitate **multiplexing**.
  - This gives us the ability to transmit multiple signals, each pertaining to a potentially different process or networked application, over the single host-to-host connection provided by IP (The Internet / Network Layer).
  - Reliability isn't the only thing that TCP provides. It also provides data encapsulation and multiplexing through the use of TCP Segments.



2. **What are the fundamental elements of reliable protocol?**

* The possibility of losing data and not being replaced means that the network up to and including the Internet Protocol is effectively an *unreliable communication channel*.  What we need to do is develop a system of rules, or a protocol, to ensure that all the data that is sent is received at the other end and in the correct order. 

* Problem: Messages can become corrupt or lost, how do you ensure the message has been successfully received?

  * Solution: Use an acknowledgment message

* Problem: what if the acknowledgment is not received?

  * Solution: re-send the message if acknowledgment is not received within a certain time frame.

* Problem: the message is received but acknowledgment is not received (or not in time), resulting in a duplicate message.

  * Solution: add sequence numbers to the messages.

    

    *What else?*

  * In-order delivery: data is received in the order that it was sent

  * Error detection: corrupt data is identified using a checksum

  * Handling data loss: missing data is retransmitted based on acknowledgments and timeouts

  * Handling duplication: duplicate data is eliminated through the use of sequence numbers

    **Our protocol as it stands is reliable. Unfortunately, it's not very efficient. ** It's a "stop and wait" system and is not an efficient use of bandwidth.

    

3. **What are pipe-lining protocols? What are its benefits?**

In computer networking, pipelining is the method of sending multiple data units without waiting for an acknowledgment for the first frame sent. Pipelining ensures better utilization of network resources and also increases the speed of delivery, particularly in situations where a large number of data units make up a message to be sent.

- To improve the throughput of our protocol, we send multiple messages after each other without waiting for acknowledgments. Reliability is still there bc we are still receiving these acknowledgments, we are just sending multiple messages at one time. 

![transport-reliability-stop-and-wait-vs-pipelining](https://da77jsbdz4r05.cloudfront.net/images/ls170/transport-reliability-stop-and-wait-vs-pipelining.png)

Both Go-back-N and Selective Repeat both use a 'window' which is the max number of messages that can be in the pipeline at any one time, and once it receives all the acknowledgments, it moves to the next window.

![transport-reliability-windowing](https://da77jsbdz4r05.cloudfront.net/images/ls170/transport-reliability-windowing.png)

BENEFITS - The advantage of this pipelined approach is its more efficient use of available bandwidth. Instead of wasting lots of time just waiting for acknowledgments, more time is spent actually transmitting data.

Finding a balance between reliability and performance is a major part of the implementation of the Transmission Control Protocol (TCP). We'll look at this protocol in more detail in the next assignment.



4. **What is a network port?**

A port is an identifier for a specific process running on a host. This identifier is an integer in the range 0-65535. 

A port is NOT a physical connection. It is a logical connection that's used by programs and services to exchange info.

It specifically determines which program or service on a computer or server is going to be used.

Always associated with an IP address- work together to exchange data on a network 



5. **What is a port number?**

- A unique number that identifies them. 

1. 0-1023 are well-known ports. These are assigned to processes that provide commonly used network services. For example, HTTP is port 80, FTP is port 20 and 21, SMTP is port 25, and so on.

2. 1024-49151 are registered ports. They are assigned as requested by private entities. For example, companies such as Microsoft, IBM, and Cisco have ports assigned that they use to provide specific services. On some operating systems, ports in this range are also used for allocation as *ephemeral ports* on the client side.

3. 49152-65535 are dynamic ports (sometimes known as private ports). Ports in this range cannot be registered for a specific use. They can be used for customized services or for allocation as *ephemeral ports*.

   

6. **What is a network socket?**

The IP address and the port number together are what enable end-to-end communication between specific applications on different machines.  The combination of IP address and port number info can be thought of as defining a `communication end-point`- generally referred to as the socket. Ex/ 216.3.128.12:8080

- The ability to programmatically instantiate socket objects specifically defined to listen for particular communications (i.e. for a certain application from a certain host) allows us to implement both connection-oriented and connectionless communication systems.
- Conceptually, a socket facilitates multiplexing. On an implementation level, instantiation of a socket object in code can implement a TCP or UDP connection specifically.

- Network sockets can be thought of as a *combination of IP address and port number*

- An abstraction for an endpoint used for inter-process communication

- At an implementation level, it can be used to refer to different specific things:

  - UNIX socket: a mechanism for communication between local processes running on the same machine.

  - Internet sockets (such as a TCP/IP socket): a mechanism for inter-process communication between networked processes (usually on different machines).

  - There *is* a distinction between the concept of a network socket and its implementation in code.

    

7. **Is TCP connectionless? Why?**

   *TCP* is a *connection-oriented* protocol. It establishes a connection using the *Three-way-handshake*

Transmission Control Protocol- Connection Oriented Protocol

Establishes a connection with the server after the data is broken down into packets from the application layer.
A connection-oriented system instantiates a new socket object to establish a dedicated virtual connection channel between two processes running on separate devices.

- When new communication comes into the first listening socket, a new socket is created that listens specifically for messages that match its **four-tuple**, i.e. the IP and port of the sender along with the IP and port of the receiver.
- This is useful for establishing specific rules of communication (i.e. message acknowledgment and in-order delivery of TCP)

- Check connections by running `netstat -ap TCP` in terminal

- TCP requires a logical connection to be established between the two processes before data is exchanged. The connection must be maintained the entire time that communication is taking place, then released afterward.

  

8. **How do sockets on the implementation level relate to the idea of protocols being connectionless or connection-oriented?**

-In socket programming or network programming terms though, the implementation of this concept involves instantiating *socket objects*. While implementations vary, many follow the Berkeley sockets API model. Implementations which follow this model define specific functions such as `bind()`, `listen()`, `accept()`, and `connect()`, among others.

-The reason for this is that having a mental model of sockets being implemented as objects helps to understand how they can be used to create *connections* between applications. Some understanding of connections is necessary to comprehend the difference between connection-oriented communication and connectionless communication. 

-By instantiating multiple socket objects, we can implement connection-oriented network communication between applications.

![transport-comms-between-processes-connectionless](https://da77jsbdz4r05.cloudfront.net/images/ls170/transport-comms-between-processes-connectionless.png)

* Connectionless - In a connectionless system we could have one socket object defined by the IP address of the host machine and the port assigned to a particular process running on that machine. That object could call a `listen()` method which would allow it to wait for incoming messages directed to that particular IP/port pair. Such messages could potentially come from any source, at any time, and in any order, but that isn't a concern in a connectionless system -- it would simply process any incoming messages as they arrived and send any responses as necessary.
  * This is useful because it is a) a simpler and more flexible process than a connection-oriented system and b) it reduces latency overhead because a connection does not have to be established.




![transport-comms-between-processes-connection-oriented](https://da77jsbdz4r05.cloudfront.net/images/ls170/transport-comms-between-processes-connection-oriented.png)

* Connection-Oriented - A connection-oriented system would work differently. You could have a socket object defined by the host IP and process port, just as in the connectionless system, also using a `listen()` method to wait for incoming messages; the difference in implementation would be in what happens when a message arrives. At this point we could instantiate a *new* socket object; this new socket object wouldn't just be defined by the local IP and port number, but also by the IP and port of the process/host which sent the message. This new socket object would then listen specifically for messages where all four pieces of information matched (source port, source IP, destination port, destination IP). The combination of these four pieces of information is commonly referred to as a **four-tuple**.  Any messages not matching this four-tuple would still be picked up by the original socket, which would then instantiate another socket object for the new connection.
  * Implementing communication in this way effectively creates a dedicated virtual connection for communication between a specific process running on one host and a specific process running on another host. The advantage of having a dedicated connection like this is that it more easily allows you to put in place rules for managing the communication such as the order of messages, acknowledgments that messages had been received, retransmission of messages that weren't received, and so on. The purpose of these types of additional communication rules is to add more reliability to the communication.
  * This is useful for establishing specific rules of communication (i.e. message acknowledgment and in-order delivery of TCP)



9. **What is a three-way handshake? What is it used for?**

In the TCP (Transmission Control Protocol) protocol. Establishing a connection with the server. This is why TCP is a connection-oriented communication. It doesn't start sending data until a connection has been established between app. processes.

1) The client sends `SYN` (synchronized) packet to the server - 'Hey server I want to establish a connection with you: a TCP Segment with the `SYN` flag set to `1`
2) The server receives it and sends back SYN-ACK (synchronized acknowledgment)- "hey I'm ready to accept the connection" : a TCP Segment with the `SYN` and `ACK` flags set to `1`
3) The client receives and sends back ACK (acknowledgment)- connection established! 
   1) Packet Transmission can start: a TCP Segment with the `ACK` flag set to `1`

* the `FIN` flag is used in a different process, the Four-way Handshake is used for terminating connections.

* Upon sending the ACK, the sender can immediately start sending application data. The receiver must wait until it has received the ACK before it can send any data back to the sender. One of the main reasons for this process is to synchronize (`SYN`) the sequence numbers that will be used during the connection.
* We want to maintain a connection state- According to RFC793
  * A connection progresses through a series of states during its lifetime. The states are: LISTEN, SYN-SENT, SYN-RECEIVED, ESTABLISHED, FIN-WAIT-1, FIN-WAIT-2, CLOSE-WAIT, CLOSING, LAST-ACK, TIME-WAIT, and the fictional state CLOSED. CLOSED is fictional because it represents the state where there is no TCB, and therefore, no connection.  Most of the time the state we are most concerned with is `ESTABLISHED`, and also `LISTEN` on the server side. The other states are related to the establishment and termination of connections.

| Client Start State | Client Action                                                | Client End State | Server Start State | Server Action                                                | Server End State |
| :----------------- | :----------------------------------------------------------- | :--------------- | :----------------- | :----------------------------------------------------------- | :--------------- |
| `CLOSED`           | Sends a `SYN` Segment                                        | `SYN-SENT`       | `LISTEN`           | Waits for a connection request                               | -                |
| `SYN-SENT`         | Waits to receive an ACK to the SYN it sent, as well as the server's `SYN` | `SYN-SENT`       | `LISTEN`           | Sends a SYN ACK Segment which serves as both it's SYN and an ACK for the client's SYN | `SYN-RECEIVED`   |
| `SYN-SENT`         | Receives the SYN ACK Segment sent by the server, and sends an ACK in response. The client is now finished with the connection establishment process | `ESTABLISHED`    | `SYN-RECEIVED`     | Waits for an ACK for the SYN it just sent                    | -                |
| `ESTABLISHED`      | Ready for data transfer. Can start sending application data. | `ESTABLISHED`    | `SYN-RECEIVED`     | Receives the ACK sent in response to its SYN. The server is now finished with the connection establishment process. | `ESTABLISHED`    |

there is an entire round-trip of latency before any application data can be exchanged. Since this hand-shake process occurs every time a TCP connection is made, this clearly has an impact on any application which uses TCP at the transport layer.  In order to help facilitate efficient data transfer once a connection is established, TCP provides mechanisms for flow control and congestion avoidance.



10. **What are multiplexing and demultiplexing?**
    - *Multiplexing* and *demultiplexing* provide for the transmission of *multiple signals over a single channel*
    - Multiplexing is enabled through the use of *network ports*

In the context of a communication network, this idea of transmitting multiple signals over a single channel is known as multiplexing, with demultiplexing being the reverse process. Takes place through the use of network ports.

Multiplexing is the transmission of multiple data inputs over a single channel of communication, such as a single device communicating with the browser, the e-mail client, and streaming Spotify all through the same Network connection.

This is important because often there are multiple applications running on a single device, and yet IP addresses only provide a single channel.

Multiplexing is implemented through the use of **port** numbers alongside IP addresses.

Each specific process is assigned a single port, which can be used to identify that same process running on a different device.

An IP address and port number combined define a communication end-point known as a **network socket**.

These sockets allow both IP and the protocol operating at the Transport Layer to transmit data between devices and processes.



11. **What is flow control? How does it work and why do we need it?**

In order to help facilitate efficient data transfer once a connection is established, TCP provides mechanisms for flow control and congestion avoidance.  Flow control is a mechanism to prevent the sender from overwhelming the receiver with too much data at once. The receiver will only be able to process a certain amount of data in a particular time frame. Data awaiting processing is stored in a 'buffer'. The buffer size will depend on the amount of memory allocated according to the configuration of the OS and the physical resources available.  Each side of a connection can let the other side know the amount of data that it is willing to accept via the WINDOW field of the TCP header. This number is dynamic and can change during the course of a connection. If the receiver's buffer is getting full it can set a lower amount in the WINDOW field of a Segment it sends to the sender, the sender can then reduce the amount of data it sends accordingly. It doesn't prevent either the sender or receiver from overwhelming the underlying network. For that task, we need a different mechanism: Congestion Avoidance.

- Provided by TCP, flow control helps to ensure that data is transmitted as efficiently as possible.
- This, in turn, helps to mitigate the increased latency inherent in TCP connections.
- Flow control is used to prevent the sender from overwhelming the receiver with too much data all at once.
- It is implemented via the window field of the TCP segment header.
  - The *window* header contains data sent by the receiver letting the sender know the maximum amount of data it can accept at any given time.
  - This number is dynamically generated, and therefore the receiver can lower the amount if the buffer is getting full, and the sender will respond accordingly.



12. **How TCP prevents the receiver's buffer from getting overloaded with data?**
    - TCP provides reliability through *message acknowledgment* and *retransmission*, and *in-order delivery*.
    - TCP also provides *Flow Control* and *Congestion Avoidance*

Flow Control 



13. **What is congestion avoidance?**

Network Congestion is a situation that occurs when there is more data being transmitted on the network than there is network capacity to process and transmit the data. You can perhaps think of it as similar to a gridlock of vehicles on a road network. Instead of things coming to a standstill, however, the 'excess vehicles' are simply lost.  In the last lesson, we looked at IP packets moving across the networks in a series of 'hops'. At each hop, the packet needs to be processed: the router at that hop runs a checksum on the packet data; it also needs to check the destination address and work out how to route the packet to the next hop on its journey to that destination. All of this processing takes time, and a router can only process so much data at once. Routers use a 'buffer' to store data that is awaiting processing, but if there is more data to be processed than can fit in the buffer, the buffer overflows and those data packets are dropped.  As we've already seen, TCP retransmits lost data. If lots of data is lost that means lots of retransmitted data, which is inefficient. Ideally, we want to keep retransmission to a minimum. TCP actually uses data loss as a feedback mechanism to detect, and avoid, network congestion; if lots of retransmissions are occurring, TCP takes this as a sign that the network is congested and reduces the size of the transmission window.

- Congestion avoidance is a service provided by TCP that attempts to prevent network congestion, a situation in which more data is being transmitted than there is capacity.
- To implement this, TCP uses data loss as a feedback mechanism to determine how "congested" the network is, by tracking how many retransmissions are required.
- A lot of data loss, or a lot of retransmissions, indicates there is more data on the network than there is the capacity to process that data.
- TCP will take this as a sign to reduce the size of the transmission window, that is, it will send fewer data along the given channel.
- This is to make data transmission as efficient as possible to mitigate the latency overhead inherent in TCP connections.



14. **What is network congestion?**

Network Congestion is a situation that occurs when there is more data being transmitted on the network than there is network capacity to process and transmit the data. You can perhaps think of it as similar to a gridlock of vehicles on a road network. Instead of things coming to a standstill, however, the 'excess vehicles' are simply lost.



15. **How do transport layer protocols enable communication between processes?**

- Network Reliability ensures that a reliable communication channel is established between processes.
- That is, all transmitted data is received at the communication end-point in the correct order.
- Consists of 4 key elements:
  - In-order delivery
  - Error detection
  - Handling data loss (ensures missing data is retransmitted)
  - Handing duplication (ensures duplicate data is eliminated)
- Network reliability is implemented by TCP in the Transport Layer.
- Lower-level protocols are inherently unreliable because they drop corrupted data with no protocols for replacement or retrieval.



16. **Disadvantages of TCP**
    - The main *downsides of TCP* are the *latency overhead of establishing a connection*, and the potential *Head-of-line blocking* as a result of in-order delivery.

Head-of-line blocking is a general networking concept and isn't specific to TCP. In general terms, it relates to how issues in delivering or processing one message in a sequence of messages can delay or 'block' the delivery or processing of the subsequent messages in the sequence.

With TCP, HOL blocking can occur as a result of the fact that TCP provides for in-order delivery of segments. Although this in-order delivery is one aspect of TCP's reliability, if one of the segments goes missing and needs to be retransmitted, the segments that come after it in the sequence can't be processed, and need to be buffered until the retransmission has occurred. This can lead to increased queuing delay which, as we saw in an [earlier assignment](https://launchschool.com/lessons/4af196b9/assignments/097d7577), is one of the elements of latency.

- TCP provides reliability at the cost of speed (that is, its reliability functions can contribute greatly to latency)

- First, there is added overhead due to the need of establishing a connection with the three-way handshake, which can add up to two round trip times.

- There is also the possibility of additional delays due to Head-of-Line blocking as a result of in-order delivery.

  - Because TCP provides in-order delivery of segments, a single segment that has a delay (say, due to being dropped and retransmitted) can "hold up" the other segments behind it in the buffer.
  - This can lead to increased queuing delays.

- It's not as flexible as other Transport Layer protocols such as UDP.

  

17. **Compare UDP and TCP. What are the similarities, and what are the differences? What are the pros and cons of using each one?**

1. TCP- A TCP Segment header contains a number of different fields. As we saw earlier in this Lesson, two of these fields -- Source Port and Destination Port -- provide the multiplexing capability of the protocol. Most of the other header fields are related to the way that TCP implements reliable data transfer.

![transport-layer-tcp-segment](https://da77jsbdz4r05.cloudfront.net/images/ls170/transport-layer-tcp-segment.png)



Some of the more important fields in the header in terms of implementing reliability are:

- CHECKSUM: The Checksum provides the Error Detection aspect of TCP reliability. It is an error-checking value generated by the sender using an algorithm. The receiver generates a value using the same algorithm and if it doesn't match, it drops the Segment. We've encountered Checksums already in this course, in other PDUs at other network layers such as IP Packets. Having a Checksum at the Transport Layer does render Checksums at lower layers redundant to a certain extent. IPv6 headers don't include a Checksum for this reason, based on the assumption that checksums are implemented at either the Transport or Link/ Data Link layers (or both).
- SEQUENCE NUMBER and ACKNOWLEDGEMENT NUMBER: these two fields are used together to provide for the other elements of TCP reliability such as In-order Delivery, Handling Data Loss, and Handling Duplication. The precise way in which TCP uses these fields is beyond the scope of this course, but it is essentially a more complex version of the simplified example of the Reliable Protocol we constructed in the previous assignment.

Other fields of interest in a typical header are the WINDOW SIZE field and the various Flag fields. The WINDOW SIZE field is related to Flow Control, which we will look at a bit later on. The Flag fields are one-bit boolean fields. A couple of these fields, `URG` and `PSH`, are related to how the data contained in the Segment should be treated in terms of its importance or urgency; we aren't going to go into exactly how these particular flags are used. The `SYN`, `ACK`, `FIN`, and `RST` flags are used to establish and end a TCP connection, as well as manage the state of that connection; we'll look at these in some more detail below.



UDP - 

- *UDP* is a very simple protocol compared to TCP. It provides *multiplexing*, but no reliability, no in-order delivery, and no congestion or flow control.
- *UDP* is *connectionless*, and so doesn't need to establish a connection before it starts sending data
- Although it is unreliable, the *advantage of UDP* is *speed* and *flexibility*.

In the previous assignment, we saw how TCP implements reliable data transfer through sequencing and retransmission of lost data, as well as providing mechanisms for flow control and congestion avoidance. So how does UDP implement all of those things? Well, basically, it doesn't. It does provide error detection.

The Protocol Data Unit (PDU) of UDP is known as a Datagram. Like all the PDUs we've looked at so far it encapsulates data from the layer above into a payload and then adds header information. If we examine the header of a UDP Datagram, we can see that it's really quite simple.

![transport-udp-datagram-header](https://da77jsbdz4r05.cloudfront.net/images/ls170/transport-udp-datagram-header.png)

Through the use of the Source and Destination Port numbers, UDP provides multiplexing in the same way that TCP does. Unlike TCP however, it doesn't do anything to resolve the inherent unreliability of the layers below it. In fact, it's probably easier to define UDP by what it *doesn't* do (particularly in comparison with TCP) than by what it *does* do.

- It provides no guarantee of message delivery
- It provides no guarantee of message delivery order
- It provides no built-in congestion avoidance or flow-control mechanisms
- It provides no connection state tracking, since it is a connectionless protocol

his simplicity provides two things to a software engineer: speed and flexibility.

UDP is a connectionless protocol. Applications using UDP at the Transport layer can just start sending data without having to wait for a connection to be established with the application process of the receiver. In addition to this, the lack of acknowledgments and retransmissions means that the actual data delivery itself is faster; once a datagram is sent it doesn't have to be sent again. Latency is less of an issue since without acknowledgments data essentially just flows one way: from sender to receiver. The lack of in-order delivery also removes the issue of Head-of-line blocking (at least at the Transport layer).  It's likely that someone building a UDP-based application will want to implement some of the services that UDP doesn't natively provide. Which services those would be, and the way they're implemented, would be up to whoever was building the application though. For example, you might want your application to have in-order delivery, but at the same time not be worried about the occasional piece of lost data. You could implement sequencing, but choose not to implement data retransmission. It is left to the software engineer to decide which services to include. These services can then be implemented at the application level, effectively using UDP as a 'base template' to build on.  Ex/ video calls, gaming 

While UDP provides a lot of flexibility and freedom, with that freedom comes a certain amount of responsibility. There are various best practices that should be adhered to. For example, it would be expected that your UDP-based application implements some form of congestion avoidance in order to prevent it from overwhelming the network.

- 
  User Datagram Protocol is a protocol that establishes end-to-end connections between processes in the Transport Layer.
- It is a very simple and *connectionless* protocol.
- Like TCP, it enables multiplexing through source and destination port numbers.
- Unlike TCP, it does not provide reliability features beyond optional error detection via a checksum.
- It makes up for this lack of reliability with its speed and flexibility.
- Specifically, UDP provides speed because it doesn't take the time to establish a dedicated connection, its lack of in-order delivery means no latency due to Head-of-Line blocking, and the one-way data flow of a connectionless system cuts down on latency due to extra round trips (there are no acknowledgments).
- Furthermore, UDP acts as a base that programmers can build upon. The specifics of what type of reliability functions to include are left up to the developer to implement at the Application level.

### UDP PDU

What is the PDU for UDP and how is it structured?

- The PDU of UDP is known as a **datagram**
- It consists of metadata in the form of headers, and a data payload, which is the encapsulated HTTP request or response from the Application Layer above.
- Its headers contain source port and destination port data, which provides for multiplexing and socket routing, information about the length of the datagram, and a checksum.

### Pros and Cons

What are the advantages and disadvantages of UDP?

- UDP does not provide any of the reliability of TCP. It is just as inherently unreliable as the layers below it.
- With UDP there is no guarantee of message delivery, delivery order, congestion avoidance, flow control, or state tracking.
- Its main advantages are speed and flexibility (see above).

### Use Cases

What are some use cases for UDP over TCP?

- UDP is a good option for any application that prioritizes speed and flexibility.
- For example, video calling applications and online games that prioritize speed over the potential for small amounts of lost data, can utilize UDP.