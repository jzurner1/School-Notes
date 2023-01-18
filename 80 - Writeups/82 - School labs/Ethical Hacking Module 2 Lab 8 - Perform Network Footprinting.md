# Description
With the IP address, hostname, and domain obtained in the previous information gathering steps, as a professional ethical hacker, your next task is to perform network footprinting to gather the network-related information of a target organization such as network range, traceroute, TTL values, etc. This information will help you to create a map of the target network and perform a man-in-the-middle attack.

# Process
1. Open the Windows 10 machine
2. Navigate to [ARIN](https://www.arin.net)
3. In the search bar, enter the IP address of a target, in this case `162.241.216.11`
4. View the available information
5. Close Firefox and open a command prompt
6. Type `tracert www.certifiedhacker.com`
	1. This will show the hops that the packets make on the way to the destination
7. Type `tracert /?` to see options for the command
8. Type `tracert -h 5 www.certifiedhacker.com` to try step 6 again, but with 5 max hops
9. Close the command prompt and switch to Parrot Security
10. Open MATE terminal
11. Type `traceroute www.certifiedhacker.com`
12. Compare this to the Windows `tracert` command