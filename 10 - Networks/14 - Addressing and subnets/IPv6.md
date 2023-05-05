# Comparison
IPv6 is the sixth version of the IP protocol, coming after IPv4. It provides virtually unlimited addresses for devices and most organizations are in the process of switching over to it.

IPv6 offers a number of advantages:
- Simplified header
	- IPv4 header has 12 fields while IPv6 has 5
- No broadcasts
- No fragmentation
- Increased address space
- Can coexist with IPv4 using dual stack or IPv6 over IPv4

# Structure
Unlike IPv4, IPv6 has 128 bits made up of eight fields of four hexadecimal digits. 4 bits are used per digit. Below is an example of one:

ABCD:0123:4040:002A:0000:0000:000A:A32D

Because this is a lot to write, there is a rule that says leading zeroes can be ignored. If multiple fields have only 0's, they can all be removed. This can only be done once per address:

ABCD:123:4040:2A::A:A32D

# Address types
- IPv6 globally routable (can travel on the internet) unicast addresses start with the first four hex characters in the range of 2000 to 3999.
- IPv6 link-local addresses start with FE80.
- Multicast addresses begin with FF.
- IPv6 can use autoconfiguration to select a new host ID using a process called EUI-64, which uses the 48-bit MAC address to generate those unique IDs. This removes the need for DHCP.
- Alternatively, IPv6 can use DHCP. This version is called DHCPv6.
- IPv6 uses NDP in the same way that IPv4 uses ARP and ICMP; to discover the network addresses and learn the MAC addresses of neighbors on the same network.

