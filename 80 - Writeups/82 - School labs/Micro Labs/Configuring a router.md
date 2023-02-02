# Description
In this lab, you will learn to configure a router. A router is a networking device that forwards data packets between computer networks. Routers perform the traffic directing functions on the Internet. A packet is typically forwarded from one router to another router through the networks that constitute an internetwork until it reaches its destination node.

# Process
1. Open the terminal connected to the switch
2. Type `en` to go to enable mode
3. Type `show ip int brief` to see the status of the interfaces
4. Type `configure terminal` to enter global configuration mode
5. Type `interface e0/3` to select an interface
6. Type `ip address 192.168.15.142 255.255.255.0` to set the IP address
7. Type `no shutdown`
8. Type `end`
9. Type `copy running-config startup-config` to save the configuration
10. Type `show ip int br` to show the statuses again