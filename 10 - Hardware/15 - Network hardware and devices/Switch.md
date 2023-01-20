A switch allows computers to communicate on a local network. They contain a number of RJ45 jacks that allow devices to connect directly through Ethernet cords. 

Unlike a [[hub|hub]], a switch has something called a CAM (content addressable memory) table that allows it to remember where devices are located. It will associate each device's [[MAC address|MAC address]] with the switch port that they are plugged into.

## Switch functions
Switches perform three primary actions:
1. Deciding when to forward or filter out a frame based on the destination MAC address
2. Preparing to forward frames by learning MAC addresses by examining the source MAC address of each frame received
3. Preparing to forward only one copy of the frame to the destination by creating a (layer 2) loop-free environment with other switches using [[STP|Spanning Tree Protocol]]
The first action is the switch's primary function while the other two are overhead functions.

## Ethernet frames
As discussed in the [[Ethernet data-link protocol|Ethernet data-link protocol]] page, switches will take in the following grame, make a decision of where to forward it, and then send the frame out that interface:

![[Pasted image 20230119152357.png]]

All Ethernet frames have both a destination and source MAC address, each of which are six bytes long (12 hexadecimal digits)

# MAC address table
## Aging
In order to keep a MAC address table updated, switches will remove entries after they aren't used for a set period of time called the aging time, usually 300 seconds (5 minutes).

To do this, each time a frame is received, the source MAC address is examined. If the MAC address isn't new, the address' inactivity timer resets to 0. If an entry's timer reaches aging time, that entry is "aged out" of the table.

## Filling the table
The other way that MAC address table entries can be removed automatically is if the table fills up. Most switches can fit upwards of 7,000 entries, so this is uncommon except on the largest networks.