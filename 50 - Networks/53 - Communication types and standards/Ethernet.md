Ethernet is a family of wired computer networking technologies commonly used in LANs, MANs, and WANs. It allows devices to communicate using a protocol.

It was designed in the early 80's and its goal is to let devices communicate in a local area such as a home or a building. It is a wired system that started with coaxial cables and has moved on to twisted-pair cables and fiber-optic cables.

It is defined by the standard IEEE 802.3 which defines the physical layer and the MAC portion of the data-link layer.

# Collision prevention
Ethernet was based on the idea that all networked devices should be eligible to transmit on a network at any time. Ethernet only permits a single frame to be on a network segment at any one time, so before a device transmits on the network, it listens to see if there is currently any traffic being sent. If there isn't, the device will transmit its data.

If two devices simultaneously listen to the network and decide that the network is empty, they will send their data. This causes a collision and results in data corruption.

### Back-off timer
Fortunately, Ethernet was designed with a mechanism to detect collisions and allow the devices that had their transmissions collided to retransmit their data at different times. After the devices notice that a collision occured, they independently set a random back-off timer, where each device waits this random amount of time before trying to transmit again. Ideally, these devices will pick different times and no collision will occur.

### CSMA/CD
The procedure to decide whether it is safe to transmit, detect collisions, and retransmit if necessary is called carrier-sense multiple access with collision detection (CSMA/CD). It has a number of components:

##### Carrier sense
A device attached to an Ethernet network can listen to the network prior to transmitting to make sure that a frame is not being transmitted on the network segment.

##### Multiple access
All Ethernet devices have access to an Ethernet segment at all time, unlike in older methods such as a token ring.

##### Collision detection
If a collision does occur, Ethernet devices can detect it and set back-off timers.

### CSMA/CA
As an Ethernet network grows, so too does the likelihood of collisions. An alternate approach is carrier-sense multiple access with collision avoidance, which is common in wireless networks.

### Ethernet switches
An Ethernet switch can be used to entirely remove collisions because each port on the switch has a single device, which in turn is a single collision domain. This means that devices do not need collision detection and they can run in full-duplex mode instead of half-duplex mode, meaning they can send and receive at the same time.


# Types and standards

Different types of ethernet have different bandwidth capacties, as seen below.

![[Pasted image 20220828213415.png]]

In addition, different ethernet standards have different capacities:

![[Pasted image 20220828213555.png]]
![[Pasted image 20220828213619.png]]
![[Pasted image 20220828213633.png]]
