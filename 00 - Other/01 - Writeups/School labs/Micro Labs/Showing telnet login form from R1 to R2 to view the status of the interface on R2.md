# Description
In this lab, you will learn to ping a host using a router. The ping command tests connectivity by sending packets to an IP address, expecting the device at that address to send packets back. The command sends packets, which means if you receive this packet, and it is addressed to you, send a reply back.

# Process
1. Connect to the terminal that is connected to the router R2
2. Type `en` to switch to enable mode
3. Type `conf t` to enter global configuration mode
4. Type `username root password 123456` to set the username and password
5. Type `line console 0` to configure the console
6. Type `login local` to use locally configured usernames and passwords
7. Type `exit` to return
8. Type `line vty 0 4` to configure telnet
9. Type `login local` to use locally configured usernames and passwords
10. Close the terminal
11. Connect to the terminal that is connected to the router R1
12. Type `telnet 192.168.107.107` to conncet to R2 with telnet
13. Log in with the earlier credentials
14. Type `show ip int br` to observe R2's IP configuration