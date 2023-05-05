# Description
In this lab, you will learn to demonstrate the difference between user and enable (privileged) modes. User mode is the first mode a user has access to after logging into the router. User mode can be identified by the `>` prompt following the router name. Enable (privileged) mode allows users to view the system configuration, restart the system, and enter router configuration mode.

# Process
1. Open PuTTY
2. Select one of the saved sessions and press open to view the switch terminal window
3. Observe that the prompt shows as `Switch>`
4. Attempt to run the `reload` command; it will fail
5. Type `enable` and press enter to go into enable mode
6. Type `reload` and press enter twice to successfully reboot the switch