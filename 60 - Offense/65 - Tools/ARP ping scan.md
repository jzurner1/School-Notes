- ARP packets are sent to discover all active devices in the IPv4 range
- For other scans to work, they may need the MAC address, so the ARP ping scan is used to obtain it
- If a response is received, the host is active; if not, it may be inactive but unsure
- [[nmap|Nmap]] uses this as the default ping scan; to use another, use `--disable-arp-ping`
- Basic nmap syntax is `nmap -sn -PR <target(s)>`

Advantages:
- Considered more efficient and accurate than other [[Host discovery|host discovery]] techniques
- Automatically handles ARP requests, retransmission, and timeout at its own discretion
- Useful for system discovery, such as over a large address space
- Can display the response time or latency of a device to an ARP packet