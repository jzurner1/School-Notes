# Description
In this lab, you will learn to configure basic passwords. By default, Cisco Catalyst switches allow full access from the console but no access via Telnet or SSH. Using default settings, a console user can move into user mode and then privileged mode with no passwords required; however, default settings prevent remote users from accessing even user mode.

# Process
1. Open PuTTY
2. Enter the given IP address and port, select Telnet, then press open
3. Type `en` to enter enable mode
4. Type `conf t` to enter terminal configuration mode
5. Type `enable secret <password>` to set the password for enable mode
6. Type `line console 0` to configure the console
7. Type `password <password>` to set the console password
8. Type `login` to enable password use
9. Type `exit` to return
10. Type `line vty 0 4` to configure Telnet
11. Type `password <password>` to set the Telnet password
12. Type `login` to enable password use
13. Type `end` to exit
14. Type `show running-config` to see the current configuration
15. Type `reload` to reset