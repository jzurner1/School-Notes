# Description
In this lab, you will learn to configure a switch to learn its IP address with DHCP (Dynamic Host Configuration Protocol). The switch can also use DHCP to dynamically learn its IPv4 settings. All you have to do is tell the switch to use DHCP on the interface and enable the interface.

# Process
1. Open PuTTY
2. Open one of the saved sessions and log in
3. Type `en` to enter enable mode
4. Type `conf t` to configure the terminal
5. Type `interface GigabitEthernet 0/3` to select an interface
6. Type `ip address dhcp` to enable DHCP
7. Type `no shutdown` to enable the interface
8. Type `end`
9. Type `show ip` to see the current IP configuration
10. Type `exit`