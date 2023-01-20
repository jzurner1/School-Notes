Spanning tree protocol is a layer 2 network protocol used to prevent looping within a network topology.

For example, look at the following network:
![[Pasted image 20230119194039.png]]
Bob's computer is off, so if Larry were to send Bob a message, it would keep looping through the switches indefinitely. This would only happen if the switches did not have Bob's MAC address in their MAC address table; they keep [[Switch decision process|flooding]] the network, looking for Bob.