Say you want to subnet the IP 172.25.0.0/16 with a 24 bit subnet.


Compare the subnet masks. The IP has 16 bits (as known by the network prefix) and the subnet has 24 bits. This means that the difference between the two is that in the original IP's subnet, the third octet is full of 0's. In the subnet, it is full of 1's.

Original subnet: 11111111 11111111 00000000 00000000
24 bit subnet:     11111111 11111111 11111111 00000000

This means that you have a range of subnets with those bits, ranging from 255.255.0.0 to 255.255.255.0. Therefore, you have the following range:

172.25.0.0/24
172.25.1.0/24
172.25.2.0/24
172.25.3.0/24
...
172.25.255.0/24