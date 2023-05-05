An [[Ethernet LAN|Ethernet LAN]] needs links between nodes in order to communicate through the network.

# Electrical signals with UTP
The most basic part of Ethernet is the electrical circuit between nodes that contains the data being transmitted.
- Each device has a receiver and a transmitter
- One wire connects the two devices at either side of a loop
- The wire is generally twisted to prevent interference
- The transmitting node changes the electrical signal over time
	- The receiver uses those same rules to decode the signal into 1's and 0's
- Typical Ethernet cords use an RJ-45 connector on both ends
	- The RJ-45 connector has eight physical pins
	- These pins create a place where the ends of the copper wires can touch the electronics inside the nodes at the end of the physical link so electricity can flow
	- Most devices have RJ-45 ports that allow Ethernet connections

# Fiber-optic cabling
Sometimes, fiber cabling is preferred to UTP. This is usually for longer distances.
- Fiber-optic cables use fiberglass as the medium through which light passes
- That light changes over time to encode 1's and 0's
- Multimode fiber has a wider core and allows LED light to pass through at multiple angles
- Single-mode fiber has a smaller core and uses laser light at a single angle
- Two cables are needed to communicate, one in each direction
- Fiber can be used with Ethernet if a switch has a compatible port