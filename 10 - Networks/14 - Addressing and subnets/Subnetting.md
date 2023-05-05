Subnetting is the process of dividing a single large network into multiple smaller networks known as [[Subnet|subnets]]. This helps relieve network congestion and improve efficiency in utilization of the relatively small address space available in IPv4.

A subnet mask is used to represent which parts of the address are for the network address and which parts are for the host address.

There are two approaches to subnetting, FLSM and VLSM.

# FLSM (Fixed Length Subnet Mask)
In FLSM, all subnets are of equal size with an equal number of host identifiers. Each subnet can have the same subnet mask, and all of the subnets have the same number of addresses in them. It is generally more wasteful than VLSM because it uses more IP addresses than are necessary.

# VLSM (Variable Length Subnet Mask)
In VLSM, the subnets can be different sizes and vary depending on how a network administrator sets them up. It is the usual standard for how networks are designed today. Each subnet uses a different subnet mask, and fewer IP addresses are wasted.

# Extending a Classful Mask
A classful mask is a subnet mask that directly represents a class. This includes masks such as 255.0.0.0, 255.255.0.0, and 255.255.255.0. To divide a network into subnets, you need to add borrowed bits to change it into a classless mask. A classless mask does not directly represent a class and has an octet that is not fully 1's or fully 0's. This may look like 11111111.11111111.11111111.11000000, which is equal to the subnet mask 255.255.255.192.