# Description
In this lab, you will learn to configure default routing. Routing enables communication between two different networks. Networks are differentiated by two different subnets. Default routing is used in forwarding packets whose destination address does not match any route in the routing table.

# Process
1. Open the terminal that is connected to the switch
2. Type `show ip route` to check the routing
3. Type `ping 192.168.1.2` to ping the given system
4. Observe that the ping fails
5. Type `conf t` to enter global configuration mode
6. Type `ip route 0.0.0.0 0.0.0.0 192.168.0.2` to configure dynamic routing
7. Type `end` to return
8. Type `copy running-config startup-config` to save the configuration
9. Type `show ip route` to check the routing again
10. Type `ping 192.168.1.2` to ping again
11. Observe that the ping succeeds this time