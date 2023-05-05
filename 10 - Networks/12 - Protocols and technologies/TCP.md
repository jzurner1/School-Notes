Transmission control protocol is a protocol that defines how to establish and maintain a network conversation. Unlike UDP, TCP is reliable, meaning that if a segment is dropped, the sender can detect that drop and retransmit the dropped segment. The receiver acknowledges each segment. Based on that, the sender can decide which segments were received and which need to be retransmitted.

![[what-is-a-tcp-3-way-handshake-process-three-way-handshaking-establishing-connection-6a724e77ba96e241.jpg]]

Below is a TCP segment's structure.

![[Pasted image 20220822211512.png]]