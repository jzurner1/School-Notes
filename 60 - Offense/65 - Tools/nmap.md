Nmap (network mapper) is a security [[Scanning|scanner]] for network exploration. It allows you to discover [[Host (networking)|hosts]], [[Port (network)|ports]], and services on a computer network.

# Syntax and help
The basic syntax for an nmap scan is `nmap [scan type] [options] {target}`.

Using `nmap -h1` or `man nmap` will provide help with most commands. The [nmap website](https://nmap.org/book/man.html) provides in-depth help.

# Basic scan types
The three most basic scan types are TCP connect scans, SYN "half-open" scans, and UDP scans. Three more less common scan types are TCP NULL scans, TCP FIN scans, and TCP Xmas scans.

TCP connect scans use a complete three-way handshake, while SYN scans send a RST flag instead of the final ACK flag. UDP scans just send packets and hope for a response.

NULL, FIN, and Xmas scans are very similar, all expecting a RST flag in response if the port is closed. They are used for firewall evasion but don't work consistently with Microsoft Windows and many CISCO networking devices.

A ping sweep is a basic way to map out a network, resulting in responses from any IP address that is occupied by a device.

If you want to find out what targets you'll be scanning without actually scanning them, you can use the `-sL` scan type. `-sL` is a list scan, meaning it will only list the IP addresses that you are targeting. This is useful if you want to make sure that you won't scan specific addresses.

# Firewall evasion
Besides the obvious stealth scans and NULL, FIN, and Xmas scans, there are a couuple more ways to evade firewalls.

If a Windows host has the default firewall set, it will block all ICMP packets. This prevents using the ping command, which nmap uses very often. This means that nmap will register a host with this firewall configuration as dead and not bother scanning it at all.

One way to avoid this is with the `-Pn` argument, which tells nmap to skip pinging a host before scanning the ports. This allows more devices to be scanned but causes it to be slower as nmap will scan every port on every IP address.

# The process
An nmap scan usually goes throught the following steps:

![[Pasted image 20221026211219.png]]

