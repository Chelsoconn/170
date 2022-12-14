

1. **Give an overview of the Link/Data Layer**

   In the OSI model, the Data Link Layer is Layer 2 and comes in between the Physical Layer(1) and the Network Layer(3).  In the Internet Protocol Suite, the Link Layer is 1.	

    * The layer is an interface between the workings of the physical network and the more logical layers above.

    * *Ethernet* is a set of standards and protocols that enables the *communication between devices on a local network*.

   * Ethernet uses a Protocol Data Unit called a Frame.

   * Ethernet uses *MAC addresses* to identify devices connected to the local network.

    * The most commonly used protocol at this layer is the `Ethernet` protocol

      * Ethernet cables connect devices on the network such as computers, switches, and routers.

      * The technical specification of these cables is governed by the same [IEEE standards](https://standards.ieee.org/standard/802_3-2018.html) that include the Ethernet communication protocols that operate at this layer of the network.

        Two of the most important aspects of Ethernet are `*framing and addressing.*`

   

   2. **What is included in an Ethernet frame?**

- DATA PAYLOAD field is used as an encapsulation mechanism for the layer 
	- An Ethernet Frame is structured data. 
	- Important parts are Destination MAC address, Source MAC address and Data Payload 
	- Interframe Gaps (IFG)- brief pause between transmission of each frame, which permits the reciever to prepare for the next frame. Contributes to the latency Transmission Delay
	- IEEE 802.3 Ethernet Standard- describes structure of frame 
	- The main elements to focus on are the Data Payload field being used as an encapsulation mechanism for the layer above, and the MAC Address fields being used to direct the frame between network devices. These particular fields exist across all the different Ethernet standards.

![Graphic showing structure of an Ethernet Frame](https://da77jsbdz4r05.cloudfront.net/images/ls170/data-link-layer-frame-structure.png)

Ethernet frames are a Protocol Data Unit, and encapsulate data from the Internet/ Network layer above. This is the lowest level of encapsulation.  Ethernet Frame adds logical structure to the physical binary data. Data in this frame are still in bits, but the structure defines which bits are actually the data payload, which are the metadata to be used in the process of transporting the frame. An ethernet- compliant network device is able to identify the different parts of the frame due to the fact that different 'fields' of data have specific lengths in bytes and appear in a set order.

- **Preamble and SFD:** The Preamble and Start of Frame Delimiter (SFD/ SOF) generally aren't considered part of the actual frame but are sent just prior to the frame as a synchronization measure which notifies the receiving device to expect frame data and then identify the start point of that data. The preamble is seven bytes (56 bits) long and the SFD is one byte (eight bits). Both use a repeated pattern that can be recognised by the receiving device, which then knows that the data following after is the frame data.
- **Source and Destination MAC address:** The next two fields, each six bytes (48 bits) long, are the source and destination MAC addresses. The source address is the address of the device which created the frame (as we'll see later on in this assignment, this can change at various points along the data's journey). The destination MAC address is the address of the device for which the data is ultimately intended. MAC Addresses are a key part of the Ethernet protocol; we'll look at them in more detail shortly.
- **Length:** the next field is two bytes (16 bits) in length. It is used to indicate the size of the Data Payload.
- **DSAP, SSAP, Control:** The next three fields are all one byte (8 bits) in length. The DSAP and SSAP fields identify the Network Protocol used for the Data Payload. The Control field provides information about the specific communication mode for the frame, which helps facilitate flow control.
- **Data Payload:** the data payload field can be between 42 and 1497 bytes in length. It contains the data for the entire Protocol Data Unit (PDU) from the layer above, an IP Packet for example.
- **Frame Check Sequence (FCS):** The final four bytes (32 bits) of an Ethernet Frame is the Frame Check Sequence. This is a checksum generated by the device which creates the frame. It is calculated from the frame data using an algorithm such as a cyclic redundancy check. The receiving device uses the same algorithm to generate a FCS and then compares this to the FCS in the sent frame. If the two don't match, then the frame is dropped. Ethernet doesn't implement any kind of retransmission functionality for dropped frames; it is the responsibility of higher level protocols to manage retransmission of lost data if this is a requirement of the protocol.











