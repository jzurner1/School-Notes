NULL, FIN, and Xmas scans are basic scan types used by nmap.

### NULL scans (-sN)
NULL scans are sent with no flags at all. The target should respond with a RST flag if the port is closed.

### FIN scans (-sF)
FIN scans are very similar but send a FIN flag. Again, the target should respond with a RST flag if the port is closed.

### Xmas scans (-sX)
Xmas scans send a malformed TCP packet and expects a RST packet in response for closed ports. It has the PSH, URG, and FIN flags set.

The goals of NULL, FIN, and Xmas scans is firewall evasion, because many firewalls are configured to drop incoming TCP packets to blocked ports which have the SYN flag set. Microsoft Windows and many CISCO networking devices are known to often respond to these three scan types with RST flags regardless of whether the port is open or not.