# Description
In this lab, you will learn to configure a Class B IP address. An IP address is an address given to a computer to identify a computer or device on the Internet. An IP address that belongs to a Class B has the first two bits in the first octet set to 10. Class B IP addresses range from 128.0.x.x to 191.255.x.x. The default subnet mask for Class B is 255.255.x.x. Class B has 16384 (2^14) Network addresses and 65534 (2^16 -2) Host addresses.

# Process
1. In the Windows 10 machine, open the network settings
2. On the right pane, select "Change adapter options"
3. In the Network Connections window, double-click Ethernet2
4. In the Status window, click properties
5. In the Properties window, in the "This connection uses the following items" section, double click IPv4
6. Select "Use the following IP address"
7. Enter `172.16.0.12` and let the subnet mask fill in by itself (`255.255.0.0`)
8. Click OK