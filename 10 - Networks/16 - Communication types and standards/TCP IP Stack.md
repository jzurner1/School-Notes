The OSI model was developed to be generic to most protocols and technologies on the internet, but most traffic on the internet is actually based on the TCP/IP protocol suite. This model is more relevant for most users and was developed by the Department of Defence. It is also known as the **TCP/IP stack** or the **DoD model**. The TCP/IP model, being a [[Networking model|networking model]], defines and references a large collection of RFC documents.

Most devices use the TCP/IP model out of the box. It is implemented by the operating system and various pieces of hardware provided by vendors.

Unlike the OSI model, there are only four defined layers. These layers are as follows:

### Application layer
- Provide services for applications, such as HTTP for web browsers
- Acts as an interface between software and the network

### Transport layer
- Fewer protocols than other layers, most common are TCP and UDP
- Provide services to the application layer such as error recovery

### Network layer
- The main protocol on this layer is the [[Internet Protocol|internet protocol (IP)]]
- Determines how to send packets through the network

### Data-link and physical layers
- These are sometimes combined into one layer
- The physical layer defines the cabling and energy (electrical signals)
- When the IP chooses to send an IP packet to another router/host, the link-layer details are used to send it



## Application protocols
All application protocols within the TCP/IP stack are identifiable by port numbers. When traffic is sent to another network node, the destination port that it will use, for example 80 for a web server. Your computer will choose a source port greater than 1023, in this example 1248.

![[Pasted image 20220823095918.png]]