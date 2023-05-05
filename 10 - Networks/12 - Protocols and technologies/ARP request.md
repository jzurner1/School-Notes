An ARP request is a broadcast sent from a device when it needs to know the MAC address associated with an IP address. It is responded to with an ARP reply.



# Packets
Here is a typical ARP request broken down:

```
0000   ff ff ff ff ff ff ac 4c a5 3f c1 70 08 06 00 01   .......L.?.p....
0010   08 00 06 04 00 01 ac 4c a5 3f c1 70 0a 00 00 01   .......L.?.p....
0020   00 00 00 00 00 00 0a 00 00 34 00 00 00 00 00 00   .........4......
0030   00 00 00 00 00 00 00 00 00 00 00 00               ............
```

Each pair of hexadecimal values represents one byte. Each of those pairs/bytes can represent one symbol, shown on the right hand side.

#### First line (0000)
The first six bytes (`ff ff ff ff ff ff`)  make up the MAC address of the destination. Sometimes it will be the MAC address of another device asking for the MAC address of the target, but usually it is a broadcast.

The next six bytes (`ac 4c a5 3f c1 70`) make up the MAC address of the sender.

The next two bytes (`08 06`) indicate the message type, in this case 0x0806, indicating that it is an ARP message.

The last two bytes on the first line (`00 01`) indicate the hardware type, in this case 0x0001, indicating Ethernet.

#### Second line (0010)
The first two bytes on the second line (`08 00`) indicate the protocol type, in this case 0x0800, indicating IPv4.

The next two bytes (`06 04`) indicates the hardware size and protocol size respectively, in this case 6 and 4.

The next two bytes (`00 01`) are the optcode, which essentially identifies the format for the rest of the packet. This one is just 1.

The next six bytes (`ac 4c a5 3f c1 70`) are the MAC address of the sender again.

The last four bytes on the second line (`0a 00 00 01`) are the IP address of the sender, in this case 10.0.0.1.

#### Third line (0020)
The first six bytes on the third line (`00 00 00 00 00 00`) indicate the target MAC address. Because this is an ARP request, those bytes are empty.

The next four bytes (`0a 00 00 34`) indicate the target IP address, in this case 10.0.0.52.

All of the 0's after that are padding.