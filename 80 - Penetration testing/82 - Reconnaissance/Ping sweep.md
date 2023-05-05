When connecting to a network for the first time, it may be helpful to obtain a "map" of the network structure, basically meaning which IP addresses contain active hosts and which do not.

The best way to do this is using nmap with a ping sweep. In a ping sweep, nmap will send an ICMP packet to every possible IP address on the specified network. When nmap receives a response from the ICMP packet, it will mark that IP address as being alive.

The switch for a ping sweep is `-sn`. The command must also include the IP addresses being targeted using either a hyphen or CIDR notation. For example, to scan the network 192.168.0.x, the commands would be:
`nmap -sn 192.168.0.1-254`
or
`nmap -sn 192.168.0.0/24`.

The `-sn` switch simply tells nmap not to scan any ports, making it rely on ICMP packets alone. It will also send a TCP SYN packet to port 443 of the target and a TCP ACK/TCP SYN packet to port 80, depending on if nmap is run with root.