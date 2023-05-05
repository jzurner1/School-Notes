An example of routing.

![[Pasted image 20220912132607.png]]

In the above figure, PC1 wants to send traffic to Server1. These two devices are on separate networks. Below gives an overview on how traffic goes from 192.168.1.2 to 192.168.3.2:

1. PC1 compares its IP address and subnet mask (192.168.1.2/24) with that of the server (192.168.3.2/24) and concludes that the destination IP address is on a different subnet. Therefore, PC1 knows that it needs to send its packets to the default gateway of the network.
2. PC1 has the default gateway of 192.168.1.1, but it doesn't know the MAC address of the gateway. To figure this out, it sends an ARP request for router R1's MAC address.

![[Pasted image 20220912133218.png]]

3. After getting an ARP reply, it adds the MAC address to its ARP cache. Then, it sends its data in a frame to the destination Server1.
4. Router R1 receives the frame from PC1 and looks at the IP header, which contains a time-to-live field, which is decremented once for each hop. Router R1 decrements the TTL field. If the value had been 0 afterward, it would have discarded the frame and sent a "time exceeded" ICMP message back to the source.
5. As long as the TTL is not 0, router R1 will check its routing table to determine the best path to reach the destination network 192.168.3.0/24. The routing table says that the network is accessible via interface Serial 1/1 (ARP is not required for serial interfaces because they don't have MAC addresses). Then, the frame is forwarded to the Serial 1/1 interface.

![[Pasted image 20220912133626.png]]

6. Again, as long as the TTL is not 0, the frame will continue on. Serial 1/1 sends out an ARP request to determine the address of server 1, and a reply is received from it. Router R2 forwards the frame outward.

![[Pasted image 20220912134007.png]]

7. The frame is now on the destination network and can be sent to the destination server.