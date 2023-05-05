The network prefix, funnily enough, is the value that comes after an IPv4 address that indicates the subnet mask of the network.

# How to find it
1. Finding a network prefix first requires you to know the subnet mask of the network. This can be done with commands such as *ipconfig*, *ifconfig*, or *ip addr*, depending on the system.
2. Next, write out the mask in binary format. For example, if the mask is 255.255.255.192, then the binary form would be 11111111.11111111.11111111.11000000.
3. Last, count up the number of consecutive 1's at the beginning of the mask. In this case there are 26 1's, so the mask would be /26.