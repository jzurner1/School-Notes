NAT (network address translation) is a service used in routers used to translate one set of IP addresses to another set. It is used to preserver the limited number of IPv4 addresses that exist around the world.

# IP addresses
There are two different types of IPv4 addresses, public and private. Public IP addresses are publicly registered on the internet, and you have to have one to have access to the internet. They are assigned by an ISP. Private IP addresses are not publicly registered and thus cannot be used to directly access the internet. They are only used internally such as in a home or a business, and they are assigned by a router.

# Why it is needed
Most homes and organizations are going to have more than one device that needs to have a connection to the internet, so those devices will need to have a public IP address. So, instead of getting a public IP address for each device, the router will get the single public IP address and provide each internal device with a private IP address.

When a device with a private IP address needs to access the internet, the address will be translated by NAT into the one public IP address for the network. NAT can translate both from private to public and public to private.

NAT will be phased out and replaced by IPv6.

# Example
The following example shows the NAT process.
![[Pasted image 20220909154102.png]]
The top row shows the devices, the second row shows the outgoing traffic, and the third row shows the incoming traffic.

In the outgoing traffic, the original packet contains a source IP that points to the host computer and the destination IP of the server on the internet. When it reaches the router, the information is changed. Now, the source IP is the router and the destination IP is the server. NAT is finished and the information is sent out on to the internet.

In the incoming traffic, the packet on the internet has the source IP of the server and the destination IP of the router. When it reaches the router, the router recognizes the source IP and changes the destination to the device that originally sent the query, in this case the host. It is sent on to the host and the process is finished.

# Related vocab
| Term                   | Definition                                         |
| ---------------------- | -------------------------------------------------- |
| Inside local address   | A private IP address referencing an inside device  |
| Inside global address  | A public IP address referencing an inside device   |
| Outside local address  | A private IP address referencing an outside device |
| Outside global address | A public IP address referencing an outside device                                                   |

![[Pasted image 20220910081442.png]]

# PAT
Also known as overload, by far the most popular. When a client sends data to the router, the router looks at the source IP, source port, destination IP, and destination IP. The router takes the private source address and replaces it with a public source address. The port number will often stay the same unless it is already being used, in which case the next available one will be used.

To keep track of which private source addresses correspond to which public source addresses, the router creates a NAT table. When a response comes back, the router will look at its public destination address and change that to the corresponding private one on the NAT table.

# DNAT
Dynamic NAT is a type of NAT that doesn't save addresses because it uses 1 to 1 mapping. To use DNAT, you need a pool of public IP addresses that must be purchased from an ISP. When information is sent from a client to the router, it looks at the destination and source address. It swaps out the source address for the first available public address in the pool, then it sends it out to the internet.

When the response is received by the router, it checks the NAT table and replaces the public destination address with the private destination address of the client. After send the data back to the client, the public address will be removed from the NAT table and is ready to use again.

# SNAT
Static NAT requires a user to manually enter addresses into the NAT table. You tell the router which private address and port number correspond to which public address and port number. Once this is done, it works just like DNAT.
