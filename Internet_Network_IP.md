1. **Give an overview of the Internet/Network Layer and it's role.**

	* OSI- network layer 3 between Data Link and Transport 

* TCP/ IP- Internet layer is 2 between Link and Transport- PREDOMINANTLY used 

- The *Internet Protocol* (IP) is the predominant protocol used for *inter-network communication*.

- There are two versions of IP currently in use: IPv4 and IPv6.

- The *Internet Protocol* uses a system of addressing (IP Addressing) to *direct data between one device and another across networks*.

- IP uses a Protocol Data Unit called a Packet.

  

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

  

1. **What is DNS and how does it work?**

   [**Domain name system**](https://www.techtarget.com/searchnetworking/definition/domain-name-system)**.** DNS is a database that includes a website's domain name, which people  use to access the website, and its corresponding IP addresses, which  devices use to locate the website. DNS translates the domain name into  IP addresses, and these translations are included within the DNS.  Servers can [cache DNS data](https://www.computerweekly.com/news/252464579/DNS-a-security-opportunity-not-to-be-overlooked-says-Nominet), which is required to access the websites. DNS also includes the DNS  protocol, which is within the IP suite and details the specifications  DNS uses to translate and communicate.

   DNS is important because it can quickly provide users with  information, as well as access to remote hosts and resources across the  internet.

   

2. **How do port numbers and IP addresses work together?**

   An IP address along with a port number create a socket.  A socket is a communications connection point (endpoint) that you can name and address in a network. Socket programming shows how to use socket APIs (application programming interface) to establish communication links between remote and local processes.  A socket is bound to a port number so that the TCP layer can identify the application that  data is destined to be sent to. An endpoint is a combination of an IP  address and a port number.

   

3. **What is a checksum and what is it used for? How is it used?**

   An error checking value generated via an algorithm. The destination device generates a value using the same algorithm and if it doesn't match, it drops the packet. IP doesn't manage retransmission of dropped packets. This is left to the layers above to implement.