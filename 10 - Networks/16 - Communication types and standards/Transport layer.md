The fourth layer of the [[OSI Model|OSI Model]]. This layer divides the upper and lower layers of the OSI model; messages from the upper layers (5-7) are taken and encapsulated into segments for transmission to the lower layers (1-3). Similarly, data streams coming from the lower layers are decapsulated and sent to the uper layers.

The previous layer is the network layer and the next layer is the session layer. The protocol data unit of this layer is the segment.

![[Pasted image 20220822201351.png]]

The two most common transport layer protocols are TCP and UDP:
- **TCP**: like other connection-oriented protocols, it offers reliable transport in that if a segment is dropped, the sender can detect the drop and retransmit that segment. A receiver also acknowledges the segments that it receives so it can determine which segments need to be retransmitted
- **UDP**: UDP is connectionless and thus offers unreliable but fast transport. If a segment is dropped, the sender is unaware of the drop and no retransmission occurs

Similar to layers 2 and 3, this layer offers flow control services. There are two common approaches:
- **Windowing**: TCP communications use windowing, meaning that segments are sent one at a time and the receiver can acknowledge them all with one ACK. Sometimes it will use a sliding window where one segment is sent then ACKed, then two segments, then four, and so on until there is no ACK received after a certain amount of time known as **round-trip time (RTT)**, also called **real transfer time**.
- **Buffering**: a device such as a router uses a chunk of memory (sometimes called a **buffer** or **queue**) to store segments if the bandwidth is not available. If the network keeps being congested, the buffer can **overflow**, meaning it will drop segments