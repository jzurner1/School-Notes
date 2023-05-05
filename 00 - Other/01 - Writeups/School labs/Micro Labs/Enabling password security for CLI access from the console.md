# Description
In this lab, you will learn to enable password security for CLI Access from the console. A Cisco switch, with default settings, remains relatively secure when locked inside a wiring closet because by default, a switch allows console access only. By default, the console requires no password at all, and no password to reach enable mode for users that happened to connect from the console.

# Process
1. Open PuTTY
2. Select one of the saved sessions and press open
3. Enter `en` to go into enable mode (same as `enable`)
4. Enter `conf t` to go into configuration mode (same as `configure terminal`)
5. Enter `hostname mySwitch` to change the hostname to `mySwitch`
6. Enter `enable secret passw0rd` to set the enable mode password to `passw0rd`
7. Enter `line console 0` to enter line configuration mode
8. Enter `password pass2` to change the user mode password
9. Enter `login`, `end`, and `exit` to return to user mode
10. Enter the password `pass2` to log in
11. Enter `en` to go into enable mode again
12. Enter the password `passw0rd` to log in
13. Enter `show running-config` to observe the current configuration