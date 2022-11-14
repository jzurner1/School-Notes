Dynamic host configuration protocol is a protocol that dynamically assigns IP addresses to network devices when they join the network. Uses UDP ports 67 and 68.

Statically assigning IP addresses to networked devices is time-consuming and error prone. Instead, most networks use DHCP to assign them dynamically. This is referred to as dynamic address assignment. The alternate approach is referred to as static assignment.

Originally, a protocol called the boostrap protocol (BOOTP) was used to assign IP addresses automatically. It is now done almost always by DHCP. Unlike BOOTP, DHCP does not require a statically configured database of MAC-address-to-IP-address mappings. It also has a wide variety of options beyond basic IP addresses, subnet masks, and default gateway parameters.

# Initialization
When a DHCP client initially boots, it follows a set of steps:
1. When it first boots, it has no IP address, default gateway, or other configuration information. It starts with a broadcast message (DHCPDISCOVER to the address 255.255.255.255) in an attempt to discover a DHCP server.
2. When a DHCP server receives a DHCPDISCOVER message, it can respond with a unicast DHCPOFFER message. Because the DHCPDISCOVER message is broadcast, it may be received and responded to by multiple DHCP servers; if that occurs, the DHCP client typically selects the first DHCPOFFER sent.
3. The DHCP client communicates with the selected server by sending a unicast DHCPREQUEST message asking the DHCP server to provide IP configuration parameters.
4. The DHCP server reponds with a unicast DHCPACK message containing a collection of IP configuration parameters.

Because a broadcast cannot cross a router boundary, if the client resides on a different network that the DHCP server, the client's next hop's router should be configured as a DHCP relay agent, which allows a router to relay DHCP requests either a unicast IP address or a directed broadcast address for a network. The DHCP relay agent may also be known as a DHCP relay or an IP helper.

# Assignment
When a network device is given an IP address through DHCP, that assignment is temporary and referred to as a lease. Alternatively, you can statically address an IP address to a MAC address, which is called a DHCP reservation.

Another frequent configuration includes an exclusion range, which is a portion of the address pool that you never want leased out to clients on the network. In addition, you can adjust the default lease time for an IP address lease.