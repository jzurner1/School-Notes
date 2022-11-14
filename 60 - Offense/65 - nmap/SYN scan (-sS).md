A SYN scan is a basic scan type used by nmap.

SYN scans, also known as "half-open" or "stealth" scans, work in a similar fashion to TCP connect scans. The only difference is that if nmap receives a TCP packet with the SYN/ACK flags set (indicating that the port is open), it will respond with a TCP packet with the RST flag set instead of the ACK flag.

The advantages of SYN scans are that they are often not logged by applications listening on open ports, and they are significantly faster than TCP scans because they do not finish the three-way handshake for every port.

If nmap is run with sudo permissions, SYN scans are the default. If it is run without sudo permissions, TCP connect scans are used instead.