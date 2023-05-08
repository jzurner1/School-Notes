ARP poisoning, also known as ARP spoofing or ARP cache poisoning, is a type of attack where malicious [[ARP|ARP]] packets are sent to a default gateway on a LAN in order to change the pairings in its IP to MAC table.

![[Pasted image 20230507201502.png]]

### How it works
Specifically, the attack begins with an attacker that has control of a device on the target LAN. The attacker then sends a false ARP reply message to the default gateway, telling it that the attacker machine's MAC address should be associated with the victim's IP address, and vice versa so the victim's MAC address should be associated with the attacker's IP address.

Next, the default gateway will save this change to its cache and send out the change to all other devices on the network. This makes it so that all of the target's traffic travels through the attacker's computer to be read or modified before being sent on to the real target.