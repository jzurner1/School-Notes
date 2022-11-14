A switch (specifically a layer 2 switch) is a [[Network device|networking device]] that can dynamically learn the MAC addresses attached to various ports by looking at the source MAC addresses on frames coming into a port. It is similar to a [[Layer 3 switch|layer 3 switch]].

For example, if switch port Gigabit Ethernet 1/1 recieved a frame with a source MAC address of DDDD.DDDD.DDDD, the switch could conclude that MAC address DDDD.DDDD.DDDD resides off port Gigabit Ethernet 1/1. In the future, if the switch receives a frame destined for MAC address DDDD.DDDD.DDDD, the switch would only send that frame out the port Gigabit Ethernet 1/1.

In contrast, a hub doesn't learn which ports contain which MAC addresses so they always send frames to all of the ports.

Whenever a switch receives a frame destined for a MAC address that is not in the switch's MAC address table, it will flood that frame out all of the ports except for the port that it was sent on. This also occurs with broadcast frames that have the destination address of FFFF.FFFF.FFFF.

# Virtual LANs (VLANs)
In a basic switch configuration, all ports on a switch belong to the same broadcast domain. A broadcast received on one port will be forwarded out all other ports. All of these devices in one broadcast domain will have the same network address and are thus in the same subnet.

# Example
Below is an example of how switching works. In it, the computer PC1 wants to form an SSH connection with the server. They both reside on the same subnet. Before starting an SSH session, PC1 needs to know the IP address and the MAC address of the server. The IP address can be found using a DNS lookup. Once that is known, PC1 will have to send out an ARP request, which is a form of broadcast. Because it is a broadcast, switches will forward it to all other ports. If this is the first time that PC1 sends a request this way, the switches will add it to their MAC address table.

![[Pasted image 20220902125408.png]]

The server will get the ARP request and respond with an ARP reply, which is not a broadcast frame. It will have a destination MAC address of PC1, making it a unicast frame. As the frame is sent back, both of the switches will add the MAC address of the server to their MAC address tables. The ARP reply will be sent only one way because the MAC address of PC1 is already on their MAC address tables.

![[Pasted image 20220902125555.png]]

Finally, PC1 will construct an SSH segment and send it to the server. When it is received, the server will respond and form a bidirectional SSH session.

![[Pasted image 20220902125926.png]]