# Description
In this lab, you will learn to display a router’s IP ARP (Address Resolution Protocol) table. The IPv4 ARP table lists the IPv4 address and matches the MAC (media access control) address of hosts connected to the same subnet as the router. When forwarding a packet to a host on the same subnet, the router encapsulates the packet with a destination MAC address as found in the ARP table.

# Process
1. Open the terminal connected to the switch
2. Type `en` to switch to enable mode
3. Type `show ip arp` to display the ARP cache