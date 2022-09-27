

1. **What is a protocol?**

   * Protocols are *systems of rules*. Network protocols are systems of rules governing the exchange or transmission of data over a network.

   1. Groups of protocols work in a layered system. Protocols at one layer provide services to the layer above.

   2. Data is encapsulated into a Protocol Data Unit, creating separation between protocols operating at different layers.

   3. The computers within a network may use vastly different software and hardware; however the use of protocols enables them to communicate with eachother regardless.

   4. ex/ Ethernet, HTTP, IP (Internet Protocol)

      

2. **What is the role of protocols?**

   In order for computers to exchange information, there must be a preexisting agreement as to how the information will be structured and how each side will send and recieve it.  The main goal is to enable systems to communicate with each other. Standardized way of communication. 

   Essentially, it allows connected devices to communicate with each other, regardless of any differences in their internal processes, structure or design.  Network protocols are the reason you can easily communicate with people  all over the world, and thus play a critical role in modern digital  communications.

   *If we didn't have protocols?*

   Network protocols were created to allow computers to communicate in an  organized manner without any room for misinterpretation. Clients that do not follow the rules oftentimes are disconnected by the server, or vice versa, depending on what the protocol specifications state.

   Without a common set of protocols that all machines connected to the Internet must follow, communication between devices couldn't happen. The various machines would be unable to understand one another or even send information in a meaningful way.

3. **Why there are many different types of protocols?**

   * Different types of protocol are concerned with different aspects of network communication. It can be useful to think of these different protocols as operating at particular 'layers' of the network.

   1. Different protocols were developed to address different aspects of network communication ex/ HTTP,TCP/UDP, IP, Ethernet

   Different needs:

   1) Need to move around and still stay connected- enhanced mobility
   2) Need for higher speeds of data exchange
   3) Need for secured exchange of info
   4) Need to reduce power consumption in data exchange
   5) Need to improve the usability of the connectors, in other words, make our life simpler. 

  - Group protocols as functioning within layers of an overall system of communication. 

    

4. **What does it mean that a protocol is stateless?**

A protocol in which each particular communication is handled as an independant event, unrelated to other similar communications.  

A Stateless Protocol is a type of network protocol in which their clients send a server request  after which the server responds based on the current state. A  Stateless Protocol doesn't require a server to retain the information of a session or the status of every communicating partner in multiple  requests.

Ex/  Domain Name System (DNS),  User Datagram Protocol (UDP), Hypertext Transfer Protocol (HTTP), etc., IP

*Benefits?*

- They simplify the overall design of a given server.
- It requires a very small number of resources. It is mainly because  the system doesn’t require keeping track of communication on multiple  links along with its session details.
- Every individual communication in the case of a Stateless Protocol is unrelated and discrete to the ones that follow or precede.
- Every package of information in a Stateless Protocol travels on its own. These packets require no reference to another packet.

*Difference between stateful protocol*

- This protocol keeps track of the connection information.
- Since it keeps a continuous track of information, it also provides better performance to its concerned clients.
- A Stateful Application always requires backing storage.
- The requests from a Stateful Protocol always depend on the state of the server’s side.
- The TCP sessions follow a Stateful type of network protocol because  both the systems in it maintain the session info during its life.
- Ex/ File Transfer Protocol, TCP

*STATEFUL WITH STATELESS*

You can't assume that any stacked protocol is stateful or stateless  just looking at the other protocols on the stack. Stateful protocols can be built on top of stateless protocols and stateless protocols can be  built on top of stateful protocols. One of the points of a layered  network model is that the kind of relationship you're looking for  (statefulness of any given protocol in function of the protocols it's  used in conjunction with) does not exist.

The TCP protocol is a stateful protocol because of what it is, not  because it is used over IP or because HTTP is built on top of it. TCP  maintains state in the form of a window size (endpoints tell each other  how much data they're ready to receive) and packet order (endpoints must confirm to each other when they receive a packet from the other). This *state* (how much bytes the other guy can receive, and whether or not he did  receive the last packet) allows TCP to be reliable even over inherently  non-reliable protocols. Therefore, TCP is a stateful protocol because it needs state to be useful.



5. **Explain briefly what are OSI and TCP/IP (internet protocol suite) models? What is the purpose of having models like that?**

 * theoretical models used to describe the networking stack.

 * The networking stack is how we maintain our sanity when talking about  networks. It is a theoretical layer cake of abstractions and  encapsulations that help isolate the many responsibilities and concerns  of networking. In reality, there’s a lot of sophisticated dovetailing of responsibilities and blurry boundaries between the layers. Ask a  network engineer how many layers there are in the networking stack, and  they will give you some number between 3 and 7.

   

1. Modularizing and structuring computer network communication models. 
   1. OSI 1-3 ~ IP 1 
   2. 4 ~ 2
   3. 5 ~ 3 
   4. 6-7 ~ 4



So Application were giving URL, Transport TCP we have ports, Internet we have IP, Link we have MAC addresses 

![Diagram comparing OSI model layers with TCP/IP layers](https://da77jsbdz4r05.cloudfront.net/images/ls170/layered-system-osi-tcp-ip-comparison.png)Each model takes a different approach. IP divides the layers in terms of the scope of communication within each layer (within local network, between networks, etc.).  OSI divides the layers in terms of the function that each layer provides (physical addressing, logical addressing and routing, encryption, compression, etc. )	

- Useful for gaining a broad- brush view of how a system works as a whole, and for modularizing different levels of responsibility within that system. 
- Developing a clear idea of how a particular protocol works and how to use it at the implementation detail is more important than trying to strictly adhere to the model. 



6. **What is PDU? What is its role?**

Protocol Data Units (PDU) - an amount or block of data transferred over a network. Referred to as different names in different layers.

In networking, a protocol data unit (PDU) is **the basic unit of exchange between entities that communicate using a specified networking protocol**

Each layer in the model uses the PDU to communicate and exchange  information, which can only be read by the peer layer on the receiving  device and is then handed over to next upper layer after stripping.

1. Consists of a header, a data payload, and in some cases a trailer/ footer

   1. Headers and footers provide protocol-specific metadata about the PDU.  Ex/ an Internet Protocol (IP) packet header would include fields for the Source IP Address and the Destination IP Address, which would be used to correctly route the packet.

   2. Data Payload- The data we want to transport over the network using a specific protocol at a particular network later

      

   7. **What is Data Payload?**

The data we want to transport over the network using a specific protocol at a particular network later 

The key to the way encapsulation is implemented. The entire PDU from a protocol at one layer is set as the data payload for a protocol at the layer below. For example, a HTTP Request at the Application layer could be set as the payload for a TCP segment at the transport layer.



![Diagram demonstrating concept of encapsulation i the context of PDUs at different network layers ](https://da77jsbdz4r05.cloudfront.net/images/ls170/layered-system-encapsulation.png)



Separation created between protocols at different layers. A protocol at one layer doesn't need to know anything about how a protocol at another layer is implemented in order for those protocols to interact. 



8. **Explain How lower-level protocols work in general?**

It can independently complete its specific communication task without information from other layers. It creates a system whereby a lower layer effectively provides a 'service' to the layer above it. In other words, a TCP segment isn't really concerned whether its data payload is an HTTP request, an SMTP command, or some other sort of Application layer data. It just knows it needs to encapsulate *some data* from the layer above and provide the result of this encapsulation to the layer below. This separation of layers provides a certain level of abstraction, which allows us to use different protocols at a certain layer without having to worry about the layers below. This is especially apparent at the Application layer, where many different protocols are used depending on the application and use case. For example, an email client would use SMTP, and web browser HTTP, and a file transfer program FTP, but all three of these programs could use TCP at the Transport layer to transfer the application layer data.

* A request for a web page moves down the layers from the browser and out  onto the network. As the request moves across the internet, various  devices will see it, modify its network headers, and pass it along.  These devices are mostly routers and switches that operate on layers 1–3 and ignore everything else. When a response comes back it will come  into the network adapter and make its way up the stack from the bottom,  ending up back in the web browser.

  

9. **What is encapsulation in the context of networking?**

* The networking stack is how we maintain our sanity when talking about  networks. It is a theoretical layer cake of abstractions and  encapsulations that help isolate the many responsibilities and concerns  of networking. In reality, there’s a lot of sophisticated dovetailing of responsibilities and blurry boundaries between the layers. Ask a  network engineer how many layers there are in the networking stack, and  they will give you some number between 3 and 7.
* *Encapsulation* is a means by which protocols at different network layers can work together.
* Encapsulation is implemented through the use of *Protocol Data Units* (PDUs). The PDU of a protocol at one layer, becomes the data payload of the PDU of a protocol at a lower layer.

1. Hiding data from one layer by encapsulating it within a data unit of the layer below. 
   1. Protocol Data Units (PDU) - an amount or block of data transferred over a network. Referred to as different names in different layers.
      1. Consists of a header, a data payload, and in some cases a trailer/ footer
         1. Headers and footers provide protocol-specific metadata about the PDU.  Ex/ an Internet Protocol (IP) packet header would include fields for the Source IP Address and the Destination IP Address, which would be used to correctly route the packet.
         2. Data Payload- The data we want to transport over the network using a specific protocol at a particular network later 

![Simple image of a PDU consisting of header and payload](https://da77jsbdz4r05.cloudfront.net/images/ls170/layered-system-pdu.png)
