The network layer provides the functional and procedural means of transferring data sequences from one node to another

The third layer of the [[OSI model|OSI model]]. This layer is primarily concerned with forwarding data based on logical addresses. The previous layer is the data link layer and the next layer is the transport layer. The PDU of this layer is the packet.

![[Pasted image 20220822200127.png]]

This layer is responsible for many tasks:
- **Logical addressing**: while the data link layer uses MAC addresses to make forwarding decisions, this layer uses logical addressing such as the internet protocol
- **Switching**: the process of making decisions about how data should be forwarded. There are three common techniques at this layer:
	- **Packet switching**: a data stream is divided into packets where each packet has a header that includes source and destination addresses. This is also called **routing**
	- **Circuit switching**: dynamically bringing up a dedicated communication link between two parties for those parties to communicate, such as an old landline service that temporarily switches a connection for the duration of the phone call
	- **Message switching**: a data stream is divided into messages where each message is tagged with a destination address. The messages travel from one network device to another on the way to their destination; they are potentially briefly stored and thus also called a **store-and-forward network**. This is not suited for real-time applications because there is delay
- **Route discovery and selection**: because layer 3 devices make decisions off of logical network addresses, they might need to know how to reach an address. A common layer 3 device is a router, which maintains a routing table indicating how to forward a packet based on the destination address.
- **Connection services**: similar to how the data link layer offers connection services for flow control and error control, connection services also exist at this layer to improve communication reliability if the data link layer's LLC sublayer is not performing those services. These functions are performed by connection services at the network layer:
	- **Flow control**: also known as **congestion control**, this helps prevent a sender from sending data more rapidly than the receiver can receive it
	- P**acket reordering**: allows packets to be placed in the proper sequences as they are sent to the reciever, which may be necessary if the packets are out of order from load balancing