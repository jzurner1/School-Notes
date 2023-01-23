This lab introduces host discovery using Nmap, Zenmap, and Angry IP Scanner.

# Description
As a professional ethical hacker or pen tester, you should be able to scan and detect the active network systems/devices in the target network. During the network scanning phase of security assessment, your first task is to scan the network systems/devices connected to the target network within a specified IP range and check for live systems in the target network.

Host discovery is considered the primary task in the network scanning process. It is used to discover the active/live hosts in a network. It provides an accurate status of the systems in the network, which, in turn, reduces the time spent on scanning every port on every system in a sea of IP addresses in order to identify whether the target host is up.

# Process
1. Log in to the provided Windows 10 machine
2. On the desktop, open Zenmap
3. In the command field, enter `nmap -sn -PR 10.10.10.16`
4. Observe the results of the ARP ping scan; the targeted host is up
5. In the command field, enter `nmap -sn -PU 10.10.10.16`
6. This is a UDP ping scan; the host is still active
7. In the command field, enter `nmap -sn -PE 10.10.10.16`
8. This is an ICMP ECHO scan, which also shows the host is active.
9. In the command field, enter `nmap -sn -PE 10.10.10.11-20`
10. This is an ICMP ECHO ping sweep, used to discover live hosts from a range; it shows that hosts with the final octet of `13`, `14`, `16`, and `19` are active
11. Close out of Zenmap and open Angry IP Scanner
12. In the IP range field, type the range as `10.10.10.0` to `10.10.10.255`
13. Open the preferences window and select the "scanning" tab
14. Under the "pinging" section, select the pinging method as "combined UDP + TCP"
15. Select the display tab; under the "display in the results list" section, select "alive hosts only" and press OK
16. Press start to begin the scan
17. After the scan finishes, observe the results; 254 hosts scanned, 4 with hosts alive