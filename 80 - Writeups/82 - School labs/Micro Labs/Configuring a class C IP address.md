# Description
In this lab, you will learn to configure a Class C IP address. An IP address is an address given to a computer to identify a computer or device on the Internet. The first octet of a Class C IP address has its first 3 bits set to 110. Class C IP addresses range from 192.0.0.x to 223.255.255.x. The default subnet mask for Class C is 255.255.255.x. Class C gives 2097152 (2^21) Network addresses and 254 (2^8 -2) Host addresses.

# Process
1. In the Windows 10 machine, open the network settings
2. On the right pane, select "Change adapter options"
3. In the Network Connections window, double-click Ethernet3
4. In the Status window, click properties
5. In the Properties window, in the "This connection uses the following items" section, double click IPv4
6. Select "Use the following IP address"
7. Enter `192.168.0.1` and let the subnet mask fill in by itself (`255.255.255.0`)
8. Click OK