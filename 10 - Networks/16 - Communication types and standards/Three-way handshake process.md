Because [[TCP|TCP]] is connection oriented (prioritized connection establishment before data transfer), it requires a way to ensure that a connection has been made.

![[what-is-a-tcp-3-way-handshake-process-three-way-handshaking-establishing-connection-6a724e77ba96e241.jpg]]

Imagine there are two computers, `10.0.0.5` (the source) and `10.0.0.6` (the destination).
1. `10.0.0.5` sends a SYN packet to `10.0.0.6`
2. When it receives the packet, the `10.0.0.6` responds with a SYN/ACK packet
3. The `10.0.0.5` sends back an ACK packet in response
4. The connection is now open, and will continue until...
5. ...One of the devices sends a FIN or RST packet
6. The other device responds with an ACK packet followed by a FIN packet
7. The connection is now closed