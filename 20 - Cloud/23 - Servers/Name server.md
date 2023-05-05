The domain name system is a system used to map IP addresses to a host naming scheme on networks. A DNS server, also known as a name server, acts as a directory lookup to find the names of servers on the local network.

Linux servers use the BIND software package to provide DNS naming services. The main program in BIND is named, a server daemon that resolves hostnames to IP addresses for clients on the local network. One BIND server can communicate with other DNS servers to look up an address on remote networks, allowing clients to point to only one DNS name server and still being able to resolve any IP address on the internet.