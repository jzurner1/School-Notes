# Description
As a professional ethical hacker or pen tester, the first step is to perform active sniffing on the target network using various active sniffing techniques such as MAC flooding, DHCP starvation, ARP poisoning, or MITM. In active sniffing, the switched Ethernet does not transmit information to all systems connected through the LAN as it does in a hub-based network.

In active sniffing, ARP traffic is actively injected into a LAN to sniff around a switched network and capture its traffic. A packet sniffer can obtain all the information visible on the network and records it for future review. A pen tester can see all the information in the packet, including data that should remain hidden.

An ethical hacker or pen tester needs to ensure that the organization’s network is secure from various active sniffing attacks by analyzing incoming and outgoing packets for any attacks.

# Process
### Task 1 - Perform MAC flooding using macof
MAC flooding is a technique used to compromise the security of network switches that connect network segments or network devices. Attackers use the MAC flooding technique to force a switch to act as a hub, so they can easily sniff the traffic.

macof is a Unix and Linux tool that is a part of the dsniff collection. It floods the local network with random MAC addresses and IP addresses, causing some switches to fail and open in repeating mode, thereby facilitating sniffing. This tool floods the switch’s CAM tables (131,000 per minute) by sending forged MAC entries. When the MAC table fills up, the switch converts to a hub-like operation where an attacker can monitor the data being broadcast.

1. In the Parrot Security machine, open Wireshark
2. Double click the eth0 interface and let the program run
3. Open MATE terminal
4. Switch to root user and navigate to the root directory
5. Type `macof -i eth0 -n 10` to run the macof command
	1. `-i` specifies the interface, `-n` specifies the number of packets
6. This command will start flooding the CAM table with random MAC addresses
7. Return to Wireshark
8. Click on any of the packets with the protocol of IPv4
9. In the packet details section, expand the Ethernet II section
10. Observe the packets sent; macof sent packets to all machines on the network with random MAC and IP addresses

### Task 2 - Perform a DHCP Starvation Attack using Yersinia
In a DHCP starvation attack, an attacker floods the DHCP server by sending a large number of DHCP requests and uses all available IP addresses that the DHCP server can issue. As a result, the server cannot issue any more IP addresses, leading to a Denial-of-Service (DoS) attack. Because of this issue, valid users cannot obtain or renew their IP addresses, and thus fail to access their network. This attack can be performed by using various tools such as Yersinia and Hyenae.

Yersinia is a network tool designed to take advantage of weaknesses in different network protocols such as DHCP. It pretends to be a solid framework for analyzing and testing the deployed networks and systems.

1. Open Wireshark in the Parrot Security machine
2. Open Wireshark
3. Double-click the eth0 interface to start scanning its traffic
4. Open MATE terminal, switch to root user, and cd to root directory
5. Type `yersinia -I`
6. Press any key to remove the noification window
7. Press `h` to open the help menu and observe the available commands
8. Press `q` to quit
9. Press the f2 key to select DHCP mode
10. Press `x` to list the available attack modes
11. Press `1` to start a DHCP starvation attack
12. After a few seconds, press `q` to quit
13. Open the Wireshark window and observe the high number of DHCP packets
14. Click on any one of them and open the Ethernet II node in the packet details section
15. Observe the addresses used

### Perform ARP Poisoning using arpspoof
ARP spoofing is a method of attacking an Ethernet LAN. ARP spoofing succeeds by changing the IP address of the attacker’s computer to the IP address of the target computer. A forged ARP request and reply packet find a place in the target ARP cache in this process. As the ARP reply has been forged, the destination computer (target) sends the frames to the attacker’s computer, where the attacker can modify them before sending them to the source machine (User A) in an MITM attack.

arpspoof redirects packets from a target host (or all hosts) on the LAN intended for another host on the LAN by forging ARP replies. This is an extremely effective way of sniffing traffic on a switch.

1. In the Parrot Security machine, open Wireshark
2. Double-click the eth0 interface to start capturing packets
3. Open MATE terminal, switch to root user, and cd to the root directory
4. Type `arpspoof -i eth0 -t 10.10.10.1 10.10.10.10`
	1. `-i` specifies the interface, `-t` specifies the targets
5. Press Ctrl+Z to stop
6. Reopen the Wireshark window and observe all the ARP packets
7. Switch back to the terminal and type `arpspoof -i eth0 10.10.10.1 10.10.10.10`
	1. This is the same command but with the IPs swapped
8. Press Ctrl+Z to stop
9. Switch back to the Wireshark window
10. Observe some of the ARP packets with the warning "duplicate ip address detected for 10.10.10.10"