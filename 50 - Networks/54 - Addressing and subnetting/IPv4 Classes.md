There are 5 classes for IPv4. Each class has a specific range of IP addresses and use.

# Class A
Class A networks are for massive networks with a large number of hosts.
| Characteristic               | Value                     |
| ---------------------------- | ------------------------- |
| Public IP range              | 1.0.0.0 - 127.0.0.0       |
| Private IP range             | 10.0.0.0 - 10.255.255.255 |
| Default subnet mask | 255.0.0.0                 |
| First octet                  | 0000 0001 - 0111 1111, 1 - 127  |
| Number of networks           | 126                       |
| Number of hosts per network  | 16,777,214                          |

# Class B
Class B networks are for medium to large networks.
| Characteristic              | Value                       |
| --------------------------- | --------------------------- |
| Public IP range             | 128.0.0.0 - 191.255.0.0     |
| Private IP range            | 172.16.0.0 - 172.31.255.255 |
| Default subnet mask                 | 255.255.0.0                 |
| First octet                 | 1000 0000 - 1011 1111, 128 - 191       |
| Number of networks          | 16,382                      |
| Number of hosts per network | 65,534                            |

# Class C
Class C networks are smaller LANs such as homes.
| Characteristic              | Value                         |
| --------------------------- | ----------------------------- |
| Public IP range             | 192.0.0.0 - 223.255.255.0     |
| Private IP range            | 192.168.0.0 - 192.168.255.255 |
| Default subnet mask                 | 255.255.255.0                 |
| First octet                 | 1100 0000 - 1101 1111, 192 - 223         |
| Number of networks          | 2,097,150                     |
| Number of hosts per network | 254                              |

# Class D
Class D networks are used for multicasting, where a single host can send a stream of data to thousands of hosts on the internet at once. It is often used for things such as audio and video streaming for IP-based cable TV networks or real-time stock data.
| Characteristic | Value |
| -------------- | ----- |
| Range          | 224.0.0.0 - 239.255.255.255      |
| First octet    | 1110 0000 - 1110 1111, 224 - 239      |

# Class E
Class E networks are for research purposes.
| Characteristic | Value                       |
| -------------- | --------------------------- |
| Range          | 240.0.0.0 - 255.255.255.255 |
| First octet    | 1111 0000 - 1111 1111, 240 - 255                            |

