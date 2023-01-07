The ethernet data-link protocol is a standard used to communicate through [[ethernet|ethernet]]. It is defined as an ethernet header, encapsulated data, and finally a trailer:

![[Pasted image 20230106143012.png]]

- **Preamble** is used for synchronization.
- **Start frame delimiter (SFD)** signals that the next byte will contain the destination MAC address field.
- **Destination** contains the MAC address of the intended recipient.
- **Source** contains the MAC address of the sender.
- **Type** defines the protocol within the frame, usually IPv4 or IPv6.
- **Data and pad** contains the data from a higher layer, sometimes with padding to meet the minimum 46 bytes.
- **Frame check sequence (FCS)** provides a method for the receiving NIC to determine whether there were any errors during transmission.