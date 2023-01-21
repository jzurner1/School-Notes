In order to access a [[Switch|switch]] with [[Telnet|Telnet]] or [[SSH|SSH]], that switch needs an [[IP address|IP address]].

While most network devices have an IP address associated with each [[Network interface card|NIC]], switches don't. Instead of assigning the IP address (called a management IP address) to one of a switch's many ports, switches use something called a **switched virtual interface (SVI)** or a **VLAN interface** that acts like the switch's own NIC.

In the image below, the switch has a conceptual host inside of it that connects to other hosts through interface VLAN 1.
![[Pasted image 20230120150011.png]]
