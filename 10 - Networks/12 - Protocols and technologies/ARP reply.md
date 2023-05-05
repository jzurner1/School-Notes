An ARP reply is a response sent from a device when it receives an ARP request asking for its MAC address. A device will know that the ARP request is asking about it specifically if the IP address matches.



# Packets
Here is a typical ARP reply broken down:

```
0000   98 48 27 ad dc 0b 4e 38 91 67 e9 6f 08 06 00 01   .H'...N8.g.o....
0010   08 00 06 04 00 02 4e 38 91 67 e9 6f 0a 00 00 34   ......N8.g.o...4
0020   98 48 27 ad dc 0b 0a 00 00 af 00 00 00 00 00 00   .H'.............
0030   00 00 00 00 00 00 00 00 00 00 00 00               ............
```

Each pair of hexadecimal values represents one byte. Each of those pairs/bytes can represent one symbol, shown on the right hand side.

#### First line (0000)
The first six bytes (`98 48 27 ad dc 0b`) indicate the destination MAC address, which is usually the device that made the ARP request in the first place.

The next six bytes (`4e 38 91 67 e9 6f`) indicate the source MAC address, which is what the ARP request was asking for.

The next two bytes (`08 06`) indicate the message type, in this case 0x0806, meaning it is an ARP message.

The last two bytes (`00 01`) are the hardware type, in this case 0x0001, meaning it is Ethernet.

#### Second line (0010)
The first two bytes on the second line (`08 00`) indicate the protocol type, in this case 0x0800, meaning IPv4.

The next two bytes (`06 04`) indicate the hardware and protocol size respectively, in this case 6 and 4.

The next two bytes (`00 02`) indicate the opcode, in this case 2, meaning reply.

The next six bytes (`4e 38 91 67 e9 6f`) indicate the source MAC address again.

The last four bytes on the second line (`0a 00 00 34`) indicate the source IP address, in this case 10.0.0.52.

#### Third line
The first six bytes on the third line (`98 48 27 ad dc 0b`) indicate the destination MAC address again.

The next four bytes (`0a 00 00 af`) indicate the destination IP address, in this case 10.0.0.175.

The rest of the 0's are padding.