This page is intended to show how the `ping` command works.

## Background
In this scenario, there are two computers, PC0 and PC1, as well as a switch called Switch0. Both PC0 and PC1 are on the same network and subnet and are connected directly through Switch0. They both use a port called FastEthernet0. PC0's IP address is `192.168.0.1` and PC1's IP address is `192.168.0.2`. PC0's FastEthernet0's MAC address is `0000.0CCE.1D8E` while PC1's FastEthernet0's MAC address is `0001.4204.250C`.

![[Pasted image 20230113231331.png]]

| Name           | PC0              | PC1              | Switch0                          |
| -------------- | ---------------- | ---------------- | -------------------------------- |
| IP address     | `192.168.0.1`    | `192.168.0.2`    |                                  |
| Adapter name(s)   | FastEthernet0    | FastEthernet0    | FastEthernet0/1, FastEthernet0/3 |
| MAC address | `0000.0CCE.1D8E` | `0001.4204.250C` |                                  |

In this scenario, PC0 will be sending an [[50 - Networks/51 - Protocols and processes/ICMP|ICMP]] packet to PC1 using the `ping` command, specifically `ping 192.168.0.2`.

## Step 1: At PC0
### Layer 3 (output)
1. Immediately after sending the `ping` command, the ping process creates an ICMP echo request message
2. Because there is no source IP address specified, it is set to the IP address of the adapter, in this case FastEthernet0 and `192.168.0.1`
3. The destination IP address is seen to be in the same subnet, so the next-hop IP address is set to the destination IP address

### Layer 2 (output)
1. The next-hop IP address is unicast, so the ARP process looks it up in the ARP table
2. The next-hop IP address is found in the ARP table, so the ARP process sets the frame's destination MAC address to the one found in the table (PC1's `0001.4204.250C`)
3. The device encapsulates the [[Protocol data unit|PDU]] into an Ethernet frame

### Layer 1 (output)
1. FastEthernet0 sends out the frame to Switch0

## Step 2: At Switch0
### Layer 1 (input)
1. FastEthernet0/3 receives the frame from PC0

### Layer 2 (input)
1. The Ethernet frame's *source* MAC address is found in the switch's MAC table
2. The frame is found to be unicast, and the switch looks in its MAC table for the *destination* MAC address

### Layer 2 (output)
1. The outgoing port is an access port; the switch sends the frame to that port

### Layer 1 (output)
1. FastEthernet0/1 sends out the frame to PC1

## Step 3: At PC1
### Layer 1 (input)
1. FastEthernet0 receives the frame

### Layer 2 (input)
1. The frame's destination MAC address matches the receiving port's MAC address
2. The device decapsulates the PDU from the ethernet frame

### Layer 3 (input)
1. The packet's destination IP address matches the device's IP address
2. The device decapsulates the packet
3. The packet is an ICMP packet, so the ICMP process manages it
4. The ICMP process receives an Echo Request message

### Layer 3 (output)
1. The ICMP process replies to the Echo Request by setting ICMP type to Echo Reply
2. The ICMP process sends an Echo Reply
3. The destination IP address is in the same subnet, so the device sets the next-hop to the destination IP address

### Layer 2 (output)
1. The next-hop IP address is unicast, so the ARP process looks it up on the ARP table
2. The next-hop IP address is in the ARP table, so the ARP process sets the frame's destination MAC address to the one found in the table (PC0's `0000.0CCE.1D8E`)
3. The device encapsulates the PDU into an Ethernet frame

### Layer 1 (output)
1. FastEthernet0 sends out the frame to Switch0

## Step 4: At Switch0
### Layer 1 (input)
1. FastEthernet0/1 receives the frame

### Layer 2 (input)
1. The frame's source MAC address is found in the switch's MAC table
2. The frame is found to be unicast, so the switch looks in its MAC table for the destination MAC address

### Layer 2 (output)
1. The outgoing port is an access port; the switch sends the frame to that port

### Layer 3 (output)
1. FastEthernet0/3 sends out the frame to PC0

## Step 5: At PC0
### Layer 1 (input)
1. FastEthernet0 receives the frame

### Layer 2 (input)
1. The frame's destination MAC address matches the receiving port's MAC address
2. The device decapsulates the PDU from the Ethernet frame

### Layer 3 (input)
1. The packet's destination IP address matches the device's IP address
2. The device decapsulates the packet
3. The packet is an ICMP packet, so the ICMP process manages it
4. The ICMP process received an Echo Reply message
5. The ping process receives that Echo Reply message


This entire process is repeated a number of times, once for each ping.