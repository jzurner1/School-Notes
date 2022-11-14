A UDP scan is a basic scan type used by nmap.

Unlike TCP connections, UDP connections are stateless, meaning that they send packets without initiating a connection with a handshake. They are more difficult and slower than the previous two scans.

When a packet is sent to an open UDP port, there will be no response. The same goes if the packet is dropped by a firewall in a filtered port. For that reason, nmap will refer to the port as being open|filtered.

If the target port is closed, the target will respond with an ICMP ping packet saying that the port is unreachable.