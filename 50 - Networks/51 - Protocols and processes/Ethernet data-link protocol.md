The ethernet data-link protocol is a [[Data-link protocols|data-link protocol]] used to communicate through [[ethernet|ethernet]].

### Format
The protocol defines the Ethernet frame as having an Ethernet header in the front, the encapsulated data in the middle, and an Ethernet trailer at the end.

![[Pasted image 20230106143012.png]]

- **Preamble** is used for synchronization.
- **Start frame delimiter (SFD)** signals that the next byte will contain the destination MAC address field.
- **Destination** contains the MAC address of the intended recipient.
- **Source** contains the MAC address of the sender.
- **Type** defines the protocol within the frame, usually IPv4 or IPv6.
- **Data and pad** contains the data from a higher layer, sometimes with padding to meet the minimum 46 bytes.
- **Frame check sequence (FCS)** provides a method for the receiving NIC to determine whether there were any errors during transmission.

![[Pasted image 20230111182436.png]]
Above is a sample frame using Wireshark.

### Addressing
When constructing the frame, the sending [[50 - Networks/50 - Other network topics/Node|node]] puts its own MAC address in the source address field and the intended destination node's MAC address in the destination address field. These [[MAC address|MAC addresses]] are also called Ethernet addresses.

### Type field
Within the Ethernet frame, the type field  identifies the type of network layer packet that sits within the frame. Typically, this determines whether the frame is IPv4 or IPv6. IPv4 frames will have a type value of 0800 while IPv6 will have a type value of 86DD.