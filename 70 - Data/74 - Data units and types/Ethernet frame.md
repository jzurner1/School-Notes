An Ethernet frame is a [[Data link layer|data link]] layer [[Protocol data unit|protocol data unit]] that relies on the [[Ethernet data-link protocol|Ethernet data-link protocol]]. It acts as a payload within other data units.

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