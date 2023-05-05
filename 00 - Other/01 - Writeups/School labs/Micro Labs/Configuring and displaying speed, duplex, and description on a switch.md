# Description
In this lab, you will learn to configure and display speed, duplex, and description on a switch. Switch interfaces that support multiple speeds (10/100 and 10/100/1000 interfaces), by default, will auto-negotiate what speed to use. However, you can configure the speed and duplex settings with the duplex {auto | full | half} and speed {auto | 10 | 100 | 1000} interface subcommands.

# Process
1. Open PuTTY
2. Select one of the presets, open it, and log in
3. Type `en` to enter enable mode
4. Type `conf t` to enter terminal configuration mode
5. Type `interface GigabitEthernet 0/6` to select an interface to modify
6. Type `duplex full` to set duplex to full
7. Type `speed 100` to set speed to 100
8. Type `description printer` to set the description to printer
9. Type `end` to exit
10. Type `show running-config interface GigabitEthernet 0/6` to see that interface's current configuration
11. Type `exit` to exit