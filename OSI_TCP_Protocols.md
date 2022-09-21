

1. **What is a protocol?**

   * Protocols are *systems of rules*. Network protocols are systems of rules governing the exchange or transmission of data over a network.

   ​			- IP = Internet Protocol

   1. a set of rules governing the exchange or transmission of data.
   2. Groups of protocols work in a layered system. Protocols at one layer provide services to the layer above.
   3. Data is encapsulated into a Protocol Data Unit, creating separation between protocols operating at different layers.
   4. The computers within a network may use vastly different software and hardware; however the use of protocols enables them to communicate with eachother regardless.
   5. ex/ Ethernet, HTTP, Wifi, Bluetooth, IP, DNS
   6. 

2. **What is the role of protocols?**

   In order for computers to exchange information, there must be a preexisting agreement as to how the information will be structured and how each side will send and recieve it.  The main goal is to enable systems to communicate with each other.

   

3. **Why there are many different types of protocols?**

   * Different types of protocol are concerned with different aspects of network communication. It can be useful to think of these different protocols as operating at particular 'layers' of the network.

   1. Different protocols weer developed to address different aspects of network communication ex communicating messages through talking TCP, UDP
      - Syntactical- order of words
      - Message transfer rules- who talks first 
   2. Different protocols were developed to address the same aspect of network communication, but in a way different way or for a specific use-case ex/ talking to friends vs teachers vs presenter HTTP
      - Rules for hiearchical communication vs casual 

   Different needs:

   1) Need to move around and still stay connected- enhanced mobility
   2) Need for higher speeds of data exchange
   3) Need for secured exchange of info
   4) Need to reduce power consumption in data exchange
   5) Need to improve the usability of the connectors, in other words, make our life simpler. 


  - Group protocols as functioning within layers of an overall system of communication. 

    

4. **What does it mean that a protocol is stateless?**

A protocol in which each particular communication is handled as an independant event, unrelated to other similar communications.  

1. ex/ HTTP, DNS

   

5. **Explain briefly what are OCI and TCP/IP (internet protocol suite) models? What is the purpose of having models like that?**

 * theoretical models used to describe the networking stack.

 * The networking stack is how we maintain our sanity when talking about  networks. It is a theoretical layer cake of abstractions and  encapsulations that help isolate the many responsibilities and concerns  of networking. In reality, there’s a lot of sophisticated dovetailing of responsibilities and blurry boundaries between the layers. Ask a  network engineer how many layers there are in the networking stack, and  they will give you some number between 3 and 7.

   

1. Modularizing and structuring computer network communication models. 
   1. OSI 1-3 ~ IP 1 
   2. 4 ~ 2
   3. 5 ~ 3 
   4. 6-7 ~ 4



So Application were giving URL, Transport TCP we have ports, Internet we have IP, Link we have MAC addresses 

![Diagram comparing OSI model layers with TCP/IP layers](https://da77jsbdz4r05.cloudfront.net/images/ls170/layered-system-osi-tcp-ip-comparison.png)Each model takes a different approach. IP divides the laters in terms of the scope of communication within each layer (within local netwrok, between networks, etc.).  OSI divides the layers in terms of the function that each layer provides (physical addressing, logical addressing and routing, encryption, compression, etc. )	

- Useful for gaining a broad- brush view of how a system works as a whole, and for modularizing different levels of responsibility within that system. 
- Developing a clear idea of how a particular protocol works and how to use it at the implementation detail is more important than trying to strictly adhere to the model. 





6. **What is PDU? What is its role?**

Protocol Data Units (PDU) - an amount or block of data transferred over a network. Referred to as different names in different layers.

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
