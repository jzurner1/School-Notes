- Similar to TCP ping scan, but UDP packets are used instead
- Default port is 40125
	- Can be configured with `DEFAULT_UDP_PROBE_PORT_SPEC`
- Response means that the host is active, errors mean offline or unreachable
- Basic nmap syntax is `nmap -sn -PU <target(s)>`

Advantages:
- Can detect systems behind firewalls that have strict TCP filtering