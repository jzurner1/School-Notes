Say that you are a network administrator overseeing 150 hosts split onto three distant networks. Each network has 50 of the hosts. You are allocated the class C address 194.121.250.0. with the subnet mask 255.255.255.0 This means that you can use the addresses 194.121.250.1 to 194.121.250.254.

Why can't you use the addresses ending with 0 or 255? Well, a host address cannot be set to the lowest possible value (0) because then that is the same as referring to a network address. The highest value (255) is reserved for broadcasts, so it can't be used either.

That means you have 254 eligible addresses for your 150 hosts. Normally this wouldn't be a problem, but because the hosts are split among three networks, it requires a bit more work.

In this case, you will want to divide your network into subnets. To do this, extend the network part of the subnet mask by one bit (added bits are called borrowed bits):

Original: 11111111 11111111 11111111 00000000 or 255.255.255.000
New:      11111111 11111111 11111111 10000000 or 255.255.255.128

You now have an original classless mask and a new classless mask. This, however, will only create two subnets, one with the fourth octet as 000 and one as 128.

Because of this, you will need to add another subnet.

First:       11111111 11111111 11111111 00000000
Second:  11111111 11111111 11111111 10000000
Third:      11111111 11111111 11111111 01000000
Fourth:    11111111 11111111 11111111 11000000

This gives four subnets of equal size, which is as close to the ideal number as you can get without going under. These four subnets have the following values and range:

Original:  194.121.250.0,     fourth octet values 1-254
First:        194.121.250.1,     fourth octet values 1-62
Second:   194.121.250.64,   fourth octet values 65-126
Third:       194.121.250.128  fourth octet values 129-190
Fourth:     194.121.250.192  fourth octet values 193-254