While the main concern with routing is ensuring that data packets reach their destinations, it is the job of quality of service (QoS) to ensure that the packets to not suffer from long delays or dropped packets.

QoS is actually a suite of technologies that allows you to strategically optimize network performance for specific traffic types. Some types of traffic such as an FTP file transfer are less sensitive to latency than others such as a VoIP calls. QoS lets you identify which types of traffic need to be sent first, how much bandwidth to allocate to various traffic types, which traffic types should be dropped first in the event of congestion, and how to make the most efficient use of the relatively limited bandwidth of an IP WAN.
# Issues from a lack of bandwidth
In a network with a lack of bandwidth, packets might suffer from one or more symptoms:

### Delay
Delay is the time requireed for a packet to travel from a source to a destination. More delay makes a connection more annoying to use.

### Jitter
Jitter is the uneven arrival of packets. For example, if a packet arrives in 30ms, then the next in 50ms, then the next in 10ms, the variation in arrival time is annoying. The delay is also called variable delay.

### Drops
Packet drops occur when a link is congested and a router's interface queue overflows. Some types of traffic, specifically UDP, do not retransmit in the event of dropped packets.


# Weakest link
Consider water flowing through a group of pipes of varying diameters. The water will only ever flow as fast as the smallest pipe will let it. The same applies to bandwidth, where the slowest link speed is the effective bandwidth between two devices.

![[Pasted image 20220913112523.png]]

In the above image, the 256kbps link is the slowest link on the connection. No matter how fast the other links go, the bandwidth will not be able to stretch beyond its smallest value (effective bandwidth) and in this case will be stuck at 256kbps.

# QoS components
There are three categories of QoS features:

### Best effort
Best-effort treatment of traffic does not truly provide QoS to that traffic because there is no reordering of packets. Best effort uses a first-in, first-out (FIFO) queuing strategy, where packets are emptied from the queue in the same order in which they entered the queue.

### Integrated services (IntServ)
IntServ is often referred to as hard QoS because it can make strict bandwidth reservations. It uses signaling among network devices to provide bandwidth reservations. Resource reservation protocol (RSVP) is an example of an IntServ approach to QoS. Because it must be configured on every router along a packet's path, the main drawback of IntServ is its lack of scalability.

### Differentiated services (DiffServ)
DiffServ differentiates between multiple traffic flows. Packets are marked and routers and switches can then make decisions (such as dropping or forwarding) based on those markings. Because it does not make an explicit reservation, it is often called soft QoS. Most modern QoS configurations are based on this.

# Policing and traffic shaping
Limiting available bandwidth is the best method of QoS. Both traffic policing and traffic shaping can accomplish this. Together, they are called traffic conditioners.

Policing can be used either for inbound or outbound traffic, and it typically discards packets that exceed the configured rate limit, basically a speed limit for specific traffic types. Because policing (which uses bytes) drops packets, resulting in retransmissions, it is recommended for higher-speed interfaces. Traffic shaping (which uses bits) buffers traffic that exceeds a configured rate, so it is recommended for slower-speed interfaces.

Because clock speeds are so fast, it can be difficult to send traffic out of an interface at a slow rate. This is done by transmitting a certain number of bits/bytes during a specific timing interval, then stopping until the time resets. This process repeats, allowing an interface to send a slower average bandwidth, also called the committed information rate (CIR). The number of bits/bytes sent during a timing interval is called the committed burst (Bc) and the timing interval is written as Tc.

### Example
Say that you have a physical line rate of 128Kbps, but the CIR is only 64Kbps. Assume that there are eight timing intervals in a second (Tc = 125ms) and during each of these intervals, 8000 bits (committed burst) are sent at the line rate. Therefore, over the period of one second, 8000 bits are sent 8 times, for a total of 64000 bits per second, which is the CIR.

![[Pasted image 20220913174904.png]]

If all the bits allocated to a timing interval are not sent, those bits/bytes can be banked and used in a future interval. The parameter that allows for this storing is called the excess burst (Be) parameter. Specifically, the Be is the maximum number of bits/bytes that can be sent in excess of the Bc during a timing interval if they are available.

### Equations
*CIR = Bc / Tc*
*Tc = Bc / CIR*