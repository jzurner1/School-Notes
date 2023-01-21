# Description
In this lab, you will learn to configure VLAN (Virtual Local Area Networks). VLANs are logical subdivisions of a switch that segregate ports from one another as if they were in different LANs. VLANs offer another way to add a layer of separation between sensitive devices and the rest of the network.

# Process
1. Type `en` to enter enable mode
2. Type `conf t` to configure the terminal
3. Type `vlan 10` to select a VLAN
4. Type `name <name>` to set the name
5. Type `exit` to return
6. Type `interface range ethernet 0/0 - 3` to select a range of interfaces
7. Type `switchport access vlan` to set the ports as access ports
8. Type `end` to exit
9. Type `copy running-config startup-config` to save the configuration
10. Type `show vlan` to show the VLAN settings