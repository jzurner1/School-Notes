# Description
As a professional ethical hacker or a pen tester, the next step after discovering active hosts in the target network is to scan for open ports and services running on the target IP addresses in the target network. This discovery of open ports and services can be performed by using various port scanning tools and techniques.

Port scanning techniques are categorized according to the type of protocol used for communication within the network.

# Process
1. In the Windows 10 machine, open MegaPing
2. Select the IP scanner option from the left pane
3. Set the IP range to `10.10.10.5` to `10.10.10.20` and hit start
4. Observe the results, which contain a TTL and status
5. On the left pane, select the port scanner option
6. In the destination address list, add `10.10.10.16`
7. Select the newly created `10.10.10.16` machine and hit start to listen to the traffic
8. Observe the results, which include the packet type, keywords, and a description
9. Close MegaPing and open NetScanTools Pro
10. Select the Manual Tools tab and click the Ping Scanner option
11. Set the IP address range to `10.10.10.5` - `10.10.10.20` and hit start
12. After the scan ends, the results will open in a new window
13. Browse the results and observe the details