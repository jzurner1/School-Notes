The data link layer corrects errors that can occur on the physical layer. It also lets you define the protocol to establish and terminate connections between two connected network devices.

The second layer of the [[OSI Model|OSI Model]]. The data link layer is concerned with:
- Packaging data into frames and transmitting them on the network
- Ensuring that the frames do not exceed the maximum transmission unit (MTU) of the physical media
- Performing error detection/correction
- Uniquely finding network devices with addresses
- Handling flow control

The previous layer is the physical layer and the next layer is the network layer. The PDU of this layer is the frame.

![[Pasted image 20220822194329.png]]

The data link layer, unlike other layers, has two distinct sublayers: MAC and LLC.

# MAC sublayer
The media access control (MAC) sublayer includes the following characteristics:
- Physical addressing: specifically, this means MAC addresses.
- Logical topology: layer 2 devices view a network as a logical topology such as a bus or ring topology
- Method of transmitting on the media: with several devices connected to a network, there needs to be some strategy for deciding when a device sends media to prevent interference

# LLC sublayer
The logical link control (LLC) sublayer includes the following characteristics:
- Connection services: when a device on a network receives a message from another device on the network, the device can give feedback to the sender in the form of an acknowledgement message. The two main functions of these messages are as follows:
	- Flow control: limits the amount of data a sender can send at one time, preventing the sender from overwhelming the receiver with too much information
	- Error control: allows the recipient of data to let the sender know whether the expected data frame was not received or if it was corrupted. The recipient figures out whether the frame is corrupt by mathematically calculating a checksum. If the checksum doesn't match the checksum sent with the data frame, the recipient can notify the sender with an ACK message that the data is corrupted
- Synchronizing transmissions: senders and receivers of data frames need to coordinate when a data frame is being transmitted and should be received. There are three methods for performing synchronization:
	- Isochronous: network devices look to a common device in the network as a clock source which creates fixed-length time slots. Network devices can determine how much free space, if any is available within a time slot and insert data into it. A time slot can hold more than one data frame.
	- Asynchronous: network devices reference their own internal clocks, and network devices do not need to synchronize their clocks. Instead, the sender places a start bit at the beginning of eah frame and a stop bit at the end of each frame. These bits tell the receiver when to monitor the medium for the presence of bits. An additional bit called the parity bit may be added at the end of each byte to detect errors.
	- Synchronous: Two network devices agree on a clocking method to show the start and end of data frames. This may be by using a separate communications channel over which a clock signal is sent. A mathematical algorithm is used to create a cyclic redundancy check (CRC), which may be matched by the sender and receiver.