A TCP connect scan is a basic scan type used by nmap.

TCP connect scans attempt to complete a three-way handshake with the target. First, nmap will send a SYN flag to the target port.

- If the target port is closed, the target will respond with a TCP packet with the RST (reset) flag set.
- If the port is open, the target will respond with a TCP packet with the SYN/ACK flags set. In turn, nmap will respond with a TCP packet with the ACK flag set to complete the handshake.
- Some firewalls are configured to just drop the packets, so the port is considered to be filtered.

If nmap is run without sudo permissions, TCP scans are the default. If it is run with root, SYN scans are used instead.