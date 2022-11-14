Address resolution protocol is a protocol used to find the MAC address associated with an IP address.

In essence, a computer that needs another's MAC address will broadcast anARP request asking who has that IP address and what their MAC address is. The computer with the matching IP address will send an ARP reply with its IP address and MAC address. Both devices will add the other device's MAC and IP addresses to their ARP table.



# Example
Take two computers, one with IP 192.168.1.1 and MAC AAA and another with IP 192.168.1.2 and MAC BBB. Call them computer A and computer B, respectively. These two computers are connected with Ethernet to form a LAN.

Say that you want to send a packet from computer A to computer B, specifically a ping. The packet will have the following information:

Source IP: 192.168.1.1
Destination IP: 192.168.1.2

Because it needs to be packaged in an Ethernet frame, more information will be added:

Source MAC: AAA
Destination MAC: ?

Because computer A doesn't know computer B's MAC address, it can't send the frame. To find out the MAC address, computer A will send an ARP request, which is a form of broadcast. The ARP request will say something along the lines of "Hello, my IP is 192.168.1.1 and my MAC address is AAA. I am looking for the MAC address of the computer with the IP 192.168.1.2. If this is you, please respond."

Computer B will receive the ARP request and add the request's IP and MAC to its ARP table. Next, computer B will send an ARP reply to computer A saying "Hello, my IP address is 192.168.1.2 and my MAC address is BBB." Computer A will receive the reply and add it to its ARP table.

Now, computer A has all the information it needs to send the Ethernet frame to computer B.