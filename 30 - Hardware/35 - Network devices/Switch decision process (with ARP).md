When a switch receives a frame, it needs to decide whether or not to forward it on each interface. This is assuming that the switch already has a complete MAC address table.

# Scenario 1: No learning
Imagine the scenario below:
![[Pasted image 20230119170604.png]]
PCs A, B (`0200.3333.3333`), C (`0200.4444.4444`), and D (`0200.2222.2222`) are all connected to a switch through ports F0/1, F0/3, F0/2, and F0/4, respectively. The switch has the following MAC address table:
![[Pasted image 20230119170908.png]]
As you can see, the MAC addresses for each output have been properly configured already.

Imagine that PC A wants to send a frame to PC D.

## Step 1
1. PC A sends the frame out of its main interface that is connected to the switch
2. The frame has a destination MAC address of `0200.2222.2222`
3. The frame arrives at the F0/1 port

## Step 2
1. The switch examines the frame and grabs the destination MAC address
2. The destination MAC address is compared to the MAC address table
3. The port F0/2 matches the destination MAC address of the frame

## Step 3
1. The switch sends the frame out the F0/2 port
2. The frame still has the destination MAC address of `0200.2222.2222`
3. The frame arrives at PC D

This scenario also works with multiple switches. Each switch will have a MAC address table that lists where to send the frame, even if that means sending to another switch that will forward it again.

# Scenario 2: Learning and flooding
Take the same example as before:
![[Pasted image 20230119170604.png]]
Except this time, the MAC address table is completely empty:
![[Pasted image 20230119180725.png]]
Again, PC A wants to send a message to PC B.

## Step 1: PC A sends the frame
1. PC A sends a frame out with the destination MAC address of `0200.2222.2222`
2. The switch receives the frame into port F0/1

## Step 2: The switch examines it
1. The switch receives the frame and examines it
2. The switch doesn't find any matches for the destination MAC address in the table
3. To find the destination, the switch sends the frame out all interfaces except F0/1
	- The frame is called an unknown [[Unicast|Unicast]] frame
	- This process is called flooding
4. While waiting for the response, the switch will add the frame's source address to the MAC address table for port F0/1

## Step 3: Receiving the flood
1. PC B, PC C, and PC D will receive a copy of the frame
2. PC B and PC C will see that the destination MAC address doesn't match their own, so they will drop the frame and not send a response
3. PC D will see that the destination MAC address matches its own
4. PC D will send a response frame out to the switch

## Step 4: Responding
1. The switch will receive PC D's response in port F0/2
2. The switch will add PC D's MAC address to the MAC address table with port F0/2
3. The switch will look in the MAC address table and find that the destination MAC address matches that of port F0/1
4. The frame will be forwarded out port F0/1
5. PC A will receive the response

After this finishes, the switch's MAC address table will have values for both PC A and PC D.