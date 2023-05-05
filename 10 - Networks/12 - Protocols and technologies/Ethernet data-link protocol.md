The ethernet data-link protocol is a [[Data-link protocols|data-link protocol]] used to communicate through [[Ethernet|Ethernet]].

### Format
The protocol defines the [[Ethernet frame|Ethernet frame]] as having an Ethernet header in the front, the encapsulated data in the middle, and an Ethernet trailer at the end.


### Addressing
When constructing the frame, the sending [[10 - Networks/11 - Architectures and types/Node|node]] puts its own MAC address in the source address field and the intended destination node's MAC address in the destination address field. These [[MAC address|MAC addresses]] are also called Ethernet addresses.

### Type field
Within the Ethernet frame, the type field  identifies the type of network layer packet that sits within the frame. Typically, this determines whether the frame is IPv4 or IPv6. IPv4 frames will have a type value of 0800 while IPv6 will have a type value of 86DD.