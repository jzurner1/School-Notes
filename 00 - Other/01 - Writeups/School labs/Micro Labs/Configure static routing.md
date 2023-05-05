# Description
In this lab, you will learn to configure static routing. Routing enables the communication between two different networks. Networks are differentiated by two different subnets. In static routing, we need to define the next hop and network both. To configure static routing, here's what you need to do:

# Process
1. Open the terminal connected to the switch
2. Type `show ip route` to check the routing
3. Type `ping 192.168.1.2` to send a ping to the given network
4. Observe that the ping fails
5. Type `conf t` to enter global configuration mode
6. Type `ip route 192.168.1.0 255.255.255.0 192.168.0.2` to add a static routing
7. Type `end` to return
8. Type `copy running-config startup-config` to save the current configuration
9. Type `show ip route` to check the routing again
10. Type `ping 192.168.1.2` to try the ping again
11. Observe that this time, the ping succeeds