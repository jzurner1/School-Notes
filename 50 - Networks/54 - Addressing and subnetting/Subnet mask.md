In TCP/IP, the parts of an IP address for the host address and the network address are not fixed. A subnet mask is used to specify what parts of the address are for what. When lined up, the 1's represent the network section and the 0's represent the host section.

For example, see the address below:
IP address:     11000000.10101000.01111011.10000100 (192.168.123.132)
Subnet mask: 11111111.11111111.11111111.00000000 (255.255.255.255)
When put together, it gives us this:
Network address: 11000000.10101000.01111011.00000000 (192.168.123.0)
Host address:        00000000.00000000.00000000.10000100 (0.0.0.132)
So from that, you can get the network address and the host address. A packet from another subnet will be sent to that network address and, once there, will be sent to the host address.

A subnet mask is used with an IPv4 address to indicate where the network section is and where the host section is. It is determined through the IP class.

| Network class | First octet value | Decimal mask  | Prefix mask |
| ------------- | ----------------- | ------------- | ----------- |
| Class A       | 1 - 126           | 255.0.0.0     | /8          |
| Class B       | 128 - 191         | 255.255.0.0   | /16         |
| Class C       | 192 - 223         | 255.255.255.0 | /24         |
| Class D       | 224 - 239          |               |             |
| Class E       | 240 - 255                  |               |             |

By knowing the first octet of an IPv4 address, you can identify the subnet mask.

A prefix mask is a form of