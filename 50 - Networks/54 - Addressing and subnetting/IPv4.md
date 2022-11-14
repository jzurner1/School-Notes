IPv4 is the most popular form of layer 3 addressing scheme. It is slowly being replaced by IPv6.

Devices on IPv4 networks use unique addresses. to communicate with each other.

# Structure
An IPv4 address is a 32-bit address that is written in dotted-decimal notation. It is split into four sections (octets) divided by a period, each section representing 8 bits. The range of values that an IPv4 address can be is 0.0.0.0 to 255.255.255.255.

![[Pasted image 20220904214621.png]]

The left-most section of an IP address is for identifying the network while the right-most section is for identifying the host.

### Network section
The network section of the IP (left side) is the unique number used for identifying the network. It is also used to identify the network class.

### Host section
The host section of the IP (right side) is the unique number used to identify machines on the network.

# Writing
IPv4 addresses are written in dotted-decimal notation, meaning it is decimal numbers seperated by decimals. This, in turn, is used to represent the true binary value of the address.

For example, the IP address 10.2.45.3 would be written as follows:
00001010 00000010 00101101 00000011
where each octet can be anywhere from 00000000 to 11111111, meaning 0 to 255.

When sharing an IP address, a subnet mask may be necessary. When written as a prefix mask, it takes the form of a slash followed by the number corresponding to the subnet (8 for class A, 16 for class B, 24 for class C). For example, the following is how the previous address would be written:
10.2.45.3/8
Because it counts as a class A network, it uses the 8.