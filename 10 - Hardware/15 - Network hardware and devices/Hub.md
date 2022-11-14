A [[network device|networking device]] that lives at layer 1. It receives bits on one port and retransmits them on all the other ports. Hubs are usually connected to other network devices with UTP cabling but some early versions supported fiber-optic connections.

There are three basic types of hubs:
- Passive: Received bits are not amplified (electrically regenerated)
- Active: Bits are regenerated on all ports other than the port on which they were received
- Smart: Usually implies an active hub with enhanced features such as SNMP

One of the biggest downsides to hubs is that all of the ports on a hub belong to the same collision domain, which is an area on a LAN on which there can only be one transmission at a time. If two devices transmit at the same time they will collide and have to be retransmitted.

Because of collisions and inefficient use of bandwidth, hubs have almost entirely been replaced with switches.

![[Pasted image 20220901170901.png]]