# Description
In this lab, you will learn to configure submodes and contexts. When using configuration mode, you move from the initial mode to global configuration mode and then into subcommand modes. Context-setting commands move you from one configuration subcommand mode, or context, to another.

# Process
1. Open PuTTY
2. Enter the given IP address and port, then select Telnet and press open
3. Enter `en` and `conf t` to go to enable mode, then configuration mode
4. Enter `hostname mySwitch` to change the hostname to `mySwitch`
5. Enter `line console 0` to go to line configuration mode
6. Enter `password passw0rd` to change the console password to `passw0rd`
7. Enter `interface ethernet0/1` to enter interface configuration mode
8. Enter `exit` and `exit` to return to enable mode