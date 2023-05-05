# Description
In this lab, you will learn to configure IPv4 on a switch. Configuring the IP address (and mask) on one VLAN interface allows the switch to send and receive IP packets with other hosts in a subnet that exists on that VLAN; however, the switch cannot communicate outside the local subnet without another configuration setting called the default gateway.

# Process
1. Open PuTTY
2. Enter the given IP address and port, select Telnet, and press open
3. Type `en` to enter enable mode
4. Type `conf t` to enter terminal configuration mode
5. Type `interface vlan 1` to select an interface
6. Type `ip address 192.168.1.200 255.255.255.0` to set an IP address and subnet mask
7. Type `no shutdown` to enable the interface
8. Type `exit`
9. Type `ip default-gateway 192.168.1.1`
10. Type `end`
11. Type `show ip int br` to show the IP configuration