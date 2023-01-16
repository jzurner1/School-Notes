## Scenario
Imagine a small LAN that contains four computers, each with an IP address numbered `192.168.0.1` (for PC1) through `192.168.0.4` (for PC4).

![[Pasted image 20230115174645.png]]

PC1 wants to send a message to PC3, and PC1 already knows the IP address of PC3. The problem arises with the fact that switches are [[Layer 2 device|layer 2 devices]] and thus work based off of [[MAC address|MAC addresses]], not IP addresses. For PC1 to communicate to PC3, it somehow needs to find PC3's MAC address. That is what ARP is used for.

## Step 1: ARP request
1. PC1 creates an ARP request frame that asks "Who is `192.168.0.3`?"
2. Because this is a broadcast frame, it has a destination MAC address of `FF-FF-FF-FF-FF-FF` which will send the frame to the switch
3. When the switch receives the frame, it will see that destination MAC address and forward it out of each other interface besides the one that received it
4. When PC2 and PC4 receive the frame, they will see that the requested IP address is not their own and they will not respond

## Step 2: ARP reply
1. When PC3 receives the frame, it will recognize the requested IP address as its own
2. PC3 will send an ARP reply back to PC1 that contains its IP address and MAC address
3. When PC1 receives PC3's MAC address, it adds it to its ARP cache