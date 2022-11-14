A number of things in networking have equations related to them which make it easier to find values.

# Subnetting
- The number of assignable IP addresses in a subnet is equal to *2h-2*, where *h* is equal to the number of host bits in a subnet.
	- For example, say that you have a class B IP address. That will have sixteen host bits and sixteen network bits. Plugging this in you get *2\*16-2*, which solves out to 30.
- To calculate the number of subnets that currently exist given a subnet mask, you can use the equation *2\*s* where *s* is equal to the number of borrowed bits.
	- For example, say you have a subnet mask that has the last octet equal to 192. Converted to binary that is equal to 11000000, which has 2 borrowed bits. Plugged in you get *2\*2* which gives 4 current subnets.
- If you need to calculate the number of borrowed bits, it is simply the bits in the classless mask minus the number of bits in the default classful mask.
	- For example, take the address 11111111 11111111 11111111 11100000. The default subnet mask here is 11111111 11111111 11111111 00000000. The classless mask has 27 bits and the classful mask has 24 bits. *27-24=3*, indicating there are 3 borrowed bits.