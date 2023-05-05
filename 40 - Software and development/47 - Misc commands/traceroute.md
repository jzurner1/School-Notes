A Linux command used to determine the router hops along the path between a source device and a destination device. It is often used for troubleshooting to see which device is having trouble. The Windows equivalent is `tracert`.

The basic syntax is `traceroute <destination IP>`. On Windows, it is `tracert <destination IP>`.

On each router hop, the packet's time to live (TTL) will decrease by 1 until it hits 0, where it will be dropped.

On Linux, consecutive packets will send UDP datagrams with increasing TTLs starting at 1. This will drop at the first router, then a TTL of 2 is sent. This will be dropped at the second router. This repeats until the original TTL is reached.

Packets will probably not follow the same route if the command is run multiple times, at least if they are not on the local network. If the TTL times out, it may be worth trying again.

# Example
To find a route from your device to tryhackme.com, do `traceroute tryhackme.com` or `tracert tryhackme.com`, depending on the operating system.