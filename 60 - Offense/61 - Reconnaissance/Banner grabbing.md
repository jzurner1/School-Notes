Banner grabbing is the process of sending a routine packet to a network service and seeing what information is returned. This may return software and protocol versions, among other information.

There are two main methods for banner grabbing:
1. Spotting the banner while trying to connect to a service such as an FTP site, and downloading the binary file/bin/ls to check the system architecture
2. Initial sequence number (ISN) analysis, identifies the differences in random number generators found in the TCP stack

There are also two types of banner grabbing:
1. **Active banner grabbing**, which applies the principle that an OS's IP stack has a unique way of responding to specially crafter TCP packets. The attacker sends a variety of malformed packets to the remote host, and the responses are compared with a database. Responses vary because different operating systems have different TCP/IP stack implementations. Nmap uses a series of nine test to determine an OS fingerprint:
	- Test 1: TCP packet with the SYN and ECN-Echo flags sent to an open TCP port
	- Test 2: TCP packet with no flags (aka NULL packet) sent to an open TCP port
	- Test 3: TCP packet with the URG, PSH, SYN, and FIN flags sent to an open TCP port
	- Test 4: TCP packet with the ACK flag sent to an open TCP port
	- Test 5: TCP packet with the SYN flag sent to a closed TCP port
	- Test 6: TCP packet with the ACK flag sent to a closed TCP port
	- Test 7: TCP packet with the URG, PSH, and FIN flags sent to a closed TCP port
	- Test 8: UDP packet sent to a closed UDP port, attempting to get an "ICMP port unreachable" message
	- Test 9: Six TCP packets with SYN flag to determine the sequence generation patterns of the TCP ISN
	The objective of these tests is to find patterns in the initial sequence of numbers that the TCP implementation chose whil responding to a connection request.
2. **Passive banner grabbing**, which captures packets from the target host through sniffing to study telltale signs that can reveal an OS. This includes:
	- Banner grabbing from error messages
	- Sniffing the network traffic
	- Grabbing from page extensions; for example, .aspx is Windows
	The four areas that typically determine the OS are:
	- Time to live on outbound packets
	- Default window size
	- Whether the DF (don't fragment) bit is set
	- Whether TOS (type of service) is set
	These can be compared to a database of signatures