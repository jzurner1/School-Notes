# Description
In this lab, you will learn to configure SSH in a router. The SSH protocol is a method for secure remote login from one computer to another.

# Process
1. Open PuTTY
2. Enter the given IP address and port, select Telnet, and press open
3. Type `en` to switch to enable mode
4. Type `conf t` to switch to terminal configuration mode
5. Type `ip domain name cisco.com` to configure the domain name
6. Type `username root password <password>` to configure the password
7. Type `username root privilege 15`
8. Type `enable password ucertify` to configure password at the privilege mode
9. Type `crypto key generate rsa` to enable SSH
10. When asked how many bits, enter `1024`
11. Type `exit` to return to enable mode
12. Type `show ip ssh` to show the SSH configuration
13. Type `conf t` to enter terminal configuration mode
14. Type `ip ssh version 2` to set the SSH version
15. Type `exit` to return to enable mode
16. Type `show ip ssh` again to see the configuration
17. Type `conf t` to enter terminal configuration mode
18. Type `line vty 0 4` to configure Telnet
19. Type `transport input ssh`
20. Type `login local`
21. Type `exec-timeout 600`, all of which configure SSH
22. Type `exit` twice