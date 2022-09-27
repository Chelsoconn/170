1. **What is a network?**

  * 2 or more computers that are linked in order to share resources or exchange data.  They may be linked 	through cables, telephone lines, radio waves, satellites, or infrared light beams. 

  Local Area Network (LAN)- confined to a small area limited to a geographic region 	

  1. Computers connected to a network are called servers or workstations 

     1. Servers generally don't have a human user and provide services like printing, faxing, software hosting, file storage and sharing, complete access control for the networks resources, etc. Tend to be more powerful than workstations. A group of servers might be located in a secure area away from humans and only accessed through the network.
     2. Workstations generally have a human user which interacts with the network through them. Desktops for example.

     * May be connected through wires and cables (fastest) or wireless through **WAPS** or wireless access points. WAP devices provide a bridge between computers and networks.  Can connect hundreds or thousands of wireless users to a network.  The `hub` or `switch` is the network bridging device that the computers are linked to. Wireless local- area Network (WLAN) connect local computers wirelessly.

  Internetwork Communication - Modem connects to Router, Switch connects to router, router from other LAN connects to that LAN's router to enable communication between networks.

  Network of networks- adds another group of routers in between communicating routers to direct network traffic.

  Connect networks in larger geographic areas. Transoceanic cabling or satellite uplinks may be used to connect this type of global network. 

  1. Uses multiplexers, bridges, and routers to connect local and metropolitan networks to global communications networks like the Internet. 



2. **What is the Internet?**
   * The internet is a vast *network of networks*. It is comprised of both the *network infrastructure* itself (devices, routers, switches, cables, etc) and the *protocols* that enable that infrastructure to function.

- A global network of billions of computers and other electonic devices.  A network of networks!

- A global computer network providing a variety of  information and communication facilities, consisting of interconnected networks using standardized communication protocols.

- Relies on physical cables. Even wireless connections like Wi-Fi and 3G/4G rely on physical cables to access the internet. 

- When you visit a website, your computer sends a request over these wires to a  server. A server is where websites are stored, and works a lot like your computers hard drive. 



3. **How does the Internet work?**

- The internet is a vast *network of networks*. It is comprised of both the *network infrastructure* itself (devices, routers, switches, cables, etc) and the *protocols* that enable that infrastructure to function.
- Protocols are *systems of rules*. Network protocols are systems of rules governing the exchange or transmission of data over a network.
- It works **by using a packet routing network that follows Internet Protocol (IP) and Transport Control Protocol (TCP)** [5]. TCP and IP work together to ensure that data transmission across  the internet is consistent and reliable, no matter which device you're  using or where you're using it.



4. **Is the Internet the same thing as a network?**

| S.NO | Network                                                      | Internet                                                     |
| :--- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| 1.   | Network is defined as the group of two or more computer systems. | Whereas internet is the interrelationship of different networks. |
| 2.   | The coverage of network is limited in comparison of internet. | While it covers large geographical area.                     |
| 3.   | It provides the link between many computers and network-enabled devices. | While it provide connection among many networks.             |
| 4.   | The types of network are: LAN, MAN, WAN, CAN and HAM.        | Whereas the types of internet is world wide web.             |
| 5.   | Through network, hundreds or a few thousands of computer system can linked simultaneously. | While through internet, millions of computer system can linked simultaneously. |
| 6.   | It requires less number of hardware devices.                 | While it requires various hardware devices.                  |



5. **What is WEB (world wide web)**

   - An information system on the internet which allows documents to be connected to other documents by hypertext links,  enabling the user to search for information by moving from one document  to another.

   - An information system enabling documents and other web resources to be accessed over the internet.

   - The internet refers to the global communication system, including hardware and infrastructure, while the web is one of the services communicated over the internet.  The Web is one of many applications built on top of the Internet.

   - The **Internet** is the backbone of the Web, the technical infrastructure that makes the Web possible



6. **What is a hub and what is it used for?**

A basic piece of network hardware that replicates a message and forwards it to all the devices on the network.

This is fine if you want to send a particular message and forward it to the entire network, but usually you want to specify which specific device the message is intended for.



7. **What is a switch and what is it used for?**

A switch is a piece of hardware to which you connect devices to create a network.  Unlike a hub, a switch uses the destination address in order to direct a frame only to the device it is intended for. A switch keeps and updates a record of MAC addresses of the devices connected to it on a MAC Address Table, and associates each address with the Ethernet port to which the device is connected on the switch.

| Switch Port | MAC Address       |
| :---------- | :---------------- |
| 1           | 00:40:96:9d:68:0a |
| 2           | 00:A0:C9:14:C8:29 |
| 3           | D8:D3:85:EB:12:E3 |
| 4           | 00:1B:44:11:3A:B7 |



8. **What is a modem and what it is used for?**

A modem is what brings the internet into your home. Maintains a connection to your ISP (internet service provider).  You have to have a motem to connect. 

A computer only reads digital signals. The internet only reads analog signals. The modem demodulates incoming analog signals into a digital signal.  It modulates outgoing digital signals to analog.  Modem = Modulate / Demodulate.  Router comes in after the modem.



9. **What is a router and what is it used for?**

Gateway of a network.  All routers on a network store a local routing table.  When an IP packet is recieved by a router, the router examines the destination IP address and matches it with a list of network addresses in its routing table.  These network addresses define a range of addresses within a particular subnet.  The matching network address will determine where in the network hierachy the subnet exists.  This will then be used to select the best route for the IP packet to travel.



10. **What are the characteristics of a physical network?**

    - Latency
    - Bandwidth
    - The *physical network* is the tangible infrastructure that transmits the electrical signals, light, and radio waves which carry network communications.

    

11. **How can we as developers deals with the limitations of physical network?**

As developers and software engineers, there's really not a lot we can do about the limitations of the physical network itself. If we want to improve the performance of the applications we build, then 

*our influence is limited to the implementation of the application in terms of how we use the higher-level protocols*.

 As we'll see later in the course, however, an understanding of these physical limitations can impact the way we think about those higher-level protocols, and therefore the decisions we make about how we use them within our applications.



12. **What is Latency?**

    - *Latency is a measure of delay*. It indicates the amount of time it takes for data to travel from one point to another.

    - Measure of the time it takes for some data to get from one point in a network to another point in a network.

      

13. **There are different types of delay that of together to determine the overall latency of a network connection. All these combined are the total latency in milliseconds (ml).**

    1. Propagation delay- amount of time for a message to travel from the sender to the reciever 
       1. Ratio between distance and speed.
    2. Transmission delay- amount of time it takes to push data onto the "link". Each of the elements in a network can be thought of as an induvidual link which are all interconnected by switches, routers, and other network devices
       1. Explore `traceroute` - 
          1. a utility for displaying the route and latency of the path across a network. Running the command should return a list of hops taken for the test data to get from your PC or laptop to the Google server. The values indicated here are the Round Trip Time for each hop.
    3. Processing delay- In a [network](https://en.wikipedia.org/wiki/Computer_network) based on [packet switching](https://en.wikipedia.org/wiki/Packet_switching), **processing delay** is the time it takes [routers](https://en.wikipedia.org/wiki/Router_(computing)) to process the [packet header](https://en.wikipedia.org/wiki/Packet_header). Processing delay is a key component in [network delay](https://en.wikipedia.org/wiki/Network_delay).
    4. Queuing Delay- Network devices such as routers can only process a certain amount of data at one time before it needs to queue or buffer the data. The amount of time in 'traffic' is the queuing delay.

    5. Last-mile Latency- A lot of the delays can take place within the parts of the network which are closest to the end points. Relates to the delays involoved in getting the network signal from your ISP's network to your home or office network.

       

    * *Round-trip Time(RTT)*- A latency calculation often used in networking is Round Trip Time.  This is the length of time for a signal to be sent, added to the length of time for an acknowledgement or response to be recieved. 



14. **How can developers decrease latency?**

The goal is always to deliver information in the shortest amount of time possible, so ensuring predictable, low latency processing is key when building a real-time application.

1) Code

   1) Inefficient algorithms are the most obvious sources of latency in code.  When possible, look for unnecessary loops or nested expensive operations in code—restructuring loops and caching expensive computation results usually help.

      

15. **What is** **Bandwidth?**
    - *Bandwidth is a measure of capacity*. It indicates the amount of data that can be transmitted in a set period of time.

- The amount of data that can be sent in a particular unit of time (typically a second)

- Increasing badwidth only lets you increase the amount of data sent, not the speed, or latency.

- Varies across the network and isn't at a constant level between the start point and the end point of our data's journey. The capacity of the core network is much higher than the part of the network infrastructure that ultimately connects to your home or office building. 

- The bandwidth that a connection receives is the lowest amount at a particular point in the overall connection. A point at which bandwidth changes from relatively high to relatively low is generally referred to as a bandwidth bottleneck.

- Low bandwidth can be an issue when dealing with large amounts of data. As we'll see later in the course, however, in many situations latency can be a much more serious limitation on the performance of a networked application.



16. **What are** **Network 'Hops'?**

* The **hop count** refers to the number of network devices through  which data passes from source to destination (depending on routing  protocol, this may include the source/destination, that is, the first  hop is counted as hop 0 or hop 1.

This is related to Last Mile latency seen in `Latency`.  The hops within the core part of the network signal from your ISP's network to your home or office network, processing, or queuing.  At the network edge, there are more frequent and shorter hops as the data is directed down the network hierarchy to the appropriate sub-network.  You can think of the network edge as the entry point into a network like a home or corporate LAN.

- The journey of a piece of data on a network isnt direct from a start point to a finish but is a journey of "hops" between nodes on the network. Think of nodes as routers that process the data and forward it to the next node on the path.
  - Run `traceroute google.com` in terminal
    - Utility for displaying the route and latency of a path across a network. Running the command should return a list of hops taken for the test data to get from your PC or laptop to the Google server. The values indicated here are the Round-Trip Time (RTT) for each hop.



17. **What is a MAC address and what is its role in network communication?**

MAC = Media Access Control Device 

Every Network-Enabled-Device has a NIC (network interface card) and is assigned a specific MAC address (physical or burned in address) when manufactured.

Ex/ `00:40:96:9d:68:0a` 

- A valid MAC address must satisfy the following conditions: **It must contain 12 hexadecimal digits**. One way to represent them is to form six pairs of the characters  separated with a hyphen (-) or colon(:). For example, 01-23-45-67-89-AB  is a valid MAC address.

- In our switch scenario, each receiving device would check its MAC Address against the Destination MAC Address in the Frame to check if it was the intended recipient. If it wasn't, then it would just ignore the frame. Hubs are inefficient bc you're sending the frame to every computer, so switch's are used.
- We can't scale the use of MAC addresses to a huge scale:
  - They are physical rather than logical. Each MAC Address is tied (burned in) to a specific physical device
  - They are flat rather than hierarchical. The entire address is a single sequence of values and can't be broken down into sub-divisions.
  - The IP is the set of rules that makes this scalable 



18. **What is IP address?**

- Unlike MAC addresses, IP addresses are logical- they are not tied to a specific device, but can be assigned as required to devices as they join a network.

- The IP address that the device is assigned must fall within a range of addresses available to the local network that the device is connected to.

1. Range is defined by a network hierarchy- the overall network is split into logical subnetworks, with each defined by the range of IP addresses available to it 

   

19. **What are the components of IP addresses?**

32 bits divided into 4 sections of eight bits each.  

An IP address is a 32-bit number that is generally displayed in dotted  decimal format, in which each octet (8 bits) of the address is displayed in decimal format, and each value is separated by period (e.g.  192.168.0.5). A less common, but often useful, way of displaying the  address is in hexadecimal.

An IPv4 address has the following format: `x . x . x . x`  where *x* is called an *octet* and must be a decimal value between 0 and 255.  Octets are separated by periods. An IPv4 address must contain three periods and four octets. The following examples are valid IPv4 addresses:   

- `1 . 2 . 3 . 4`
- `01 . 102 . 103 . 104 `

An IPv6 (Normal) address has the following format:  ` y : y : y : y : y : y : y : y ` where *y* is called a *segment* and can be any hexadecimal value between 0 and FFFF. The segments are separated by colons - not periods.  An IPv6 normal address must have eight segments, however a short form notation can be used in the Tape Library Specialist Web interface for segments that are zero, or those that have leading zeros. The short form notation can not be used from the operator panel.



20. **Why do we need both MAC addresses and IP addresses?**

MAC addresses - Who you are (physical)- Who lives there?- DATA LINK 

IP- Where you are (logical)- like a home address- changes each time- NETWORK

Need both working in different ways.

```
1) MAC used to identify a device while IP is used to locate a device
1) MAC is resposible for local identification, IP for global
```

The routers send out ARP broadcast to get MAC address of next router. IP address lets you know final address.

