Denial of service is an overarching name for attacks that try to prevent accessing a site. It sends a target system a flood of data or requests that consume the target system's resources. Alternatively, some applications and operating systems crash when they receive specific strings of improperly formatted data, which can be used to take down a system. The attack often uses a spoofed IP address to conceal their identity. It is different than a [[DDoS|DDoS]] attack.

The two general types of DoS attacks are as follows:
- **Reflective**: A third party system is used to help carry out the attack. Often, the third party is not compromised, making the reflective attack difficult to track down.
- **Amplified**: A DNS server is usually used in this, but other services could be used too. In an amplified DoS attack, legitimate servers are tricked into flooding responses at a target system. The forged requests are small but there are many of them at once. It can be difficult to mitigate because the server involved (called the reflector server) is a legitimate device.

For all DoS attacks, there are some common methods:
- Flooding the victim's system with more traffic than it can handle
- Flooding a service with more vents than it can handle
- Crashing a TCP/IP stack with corrupt packets
- Crashing a service by interacting with it in an unexpected matter
- Hanging a service by causing it to go into an infinite loop

# Categories of attack vectors
DoS and DDoS attacks have similar attack vectors.
- **Volumetric attacks**: Exhausting the bandwidth within the target or between the target and the rest of the internet. This will cause traffic blockage, preventing access to legitimate users.
	- A **flood attack** is one type of this, where zombies send large volumes of traffic to the victim's systems to exhaust the bandwidth
	- An **amplification attack** is another type, where the attacker of zombies transfer messages to a broadcast IP address, which amplifies malicious traffic
	- Common examples include UDP flood attacks, ICMP flood attacks, ping of death (PoD) attacks, smurf attacks, pulse wave attacks, malformed IP packet flood attacks, and spoofed IP packet flood attacks
- **Protocol attacks**: Consuming resources other than bandwidth, such as connection state tables present in network infrastructure devices. No new connections will be allowed because the device will be waiting for existing connections to close or expire
	- Common examples include SYN flood attacks, SYN-ACK flood attacks, fragmentation attacks, ACK flood attacks, PUSH ACK flood attacks, spoofed session flood attacks, TCP connection flood attacks, ACK flood attacks, TCP state exhaustion attacks, and RST attacks
- **Application layer attacks**: Attempting to exploit vulnerabilities in the application layer protocol or in the application itself to prevent legitimate users from accessing the application. These do not require as much bandwidth as other methods to succeed. Resources are consumed by opening connections and leaving them open until no new connections can be made, destroying a specific aspect of an application or service. They are also difficult to detect and mitigate.
	- Common examples include HTTP flood attacks, slowloris attacks, and UDP application layer flood attacks.