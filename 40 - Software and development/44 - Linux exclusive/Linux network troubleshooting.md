
# Sending test packets
The basic ping command is useful for testing connections by shooting a packet to a specific address. By default, you can let it run as long as you want and, when it stops, see what percent of packets made it through.

`ping6` is the equivalent for IPv6, but you have to specify which network interface to send the packets out on. This is done by adding `%<interface name>` right after the destination IPv6 address.

Unfortunately, ping doesn't work with many hosts because often ICMP packets will just be dropped by default to prevent DoS attacks.

# Finding host information
Sometimes the network connectivity is fine but the DNS hostname system is having issues. You can test this with the `host` command, which will tell you more information about a host. For example, `host www.linux.org` will give you more information about the linux.org website, assuming it can reach it.

Alternatively you can use the dig or nslookup commands

# Netstat
The netstat command gives a lot of information about IP-based connections. With the 
 `-s` flag, it can tell you how busy your Linux system is and if there's a specific problem with one of the protocols.