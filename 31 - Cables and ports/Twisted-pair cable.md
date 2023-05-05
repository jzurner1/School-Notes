Today's most popular LAN media type is a twisted-pair [[Cable|Cable]], in which individually insulated copper strands are intertwined. Two categories are shielded twisted pair (STP) and unshielded twisted pair (UTP). A UTP coupler can be used to connect two UTP cables back-to-back.

Originally the industry standard was described in TIA/EIA-568, the original of which has come to be known as TIA/EIA-568A. In 2001, an updated standard was released that came to be known as TIA/EIA-568B. Both of the pinouts are the same but the color coding is different. 568B is more commonly used today.

# Shielded
If the cables in a wire are not twisted or shielded, it can act as an antenna that can receive or transmit EMI. To prevent this, the wires (which are individually insulated) are twisted together in pairs. If the distance between the twists is less than a quarter of the wavelength of an electromagnetic waveform, the twisted pair of wires will not radiate that wavelength or receive EMI from that wavelength. However, as frequencies increase, the wavelengths decrease.

One option for supporting higher frequencies is to surround a twisted pair in a metallic shielding similar to the outer conductor in a coaxial cable. This is referred to as shielded twister-pair (STP) cable. The main drawback is that the addition of the metal shielding makes the cable more expensive.

![[Pasted image 20220828210112.png]]

# Unshielded
Another method for blocking EMI is to twist the strands more tightly. Because there is no metal shielding, this cabling is cheaper and has become the media of choice for most LANs.

![[Pasted image 20220828210240.png]]

## Categories
UTP cables vary in their data-carrying capacity and their standards.
- Category 5: Commonly used in Ethernet 100BASE-TX networks, they can carry data at a rate of 100Mbps, but they can carry ATM traffic at 155Mbps. These consist of four pairs of 24-gauge wires where each pair is twisted with a different number of twists per meter; the average is one twist every 5cm.
- Category 5e: This is an updated version of category 5 that is commonly used for 1000BASE-T networks, which can carry data at a rate of 1Gbps. It offers reduced crosstalk as well.
- Category 6: Similar to 5e, cat 6 is commonly used for 1000BASE-T Ethernet networks. It can be made of thicker conductors but is often the same gauge of wire as 5 and 5e. It has thicker insulation and more reduced crosstalk.
- Category 6a: Also known as augmented cat 6, it supports twice as many frequencies as cat 6 and can be used for 10GBASE-T networks, which can transmit data at a rate of up to 10 billion bits per second (10Gbps).
- Category 7: Cat 7 is not an IEEE standard and is thus not very popular. It supports 10Gbps over 100m using copper media.
- Category 8: Capable of up to 40Gbps, cat 8 can only stretch up to 30 to 36 meters depending on the patch cables used. These short distances and high speeds are ideal in a data center between high-speed multilayer switches.
More categories of UTP cables existy but are not as common.

# Connectors
Common connectors for twisted-pair cables are as follows:
- RJ45: Called a type 45 registered jack, RJ45 is an 8-pin connector found in most ethernet networks, but most implementations use only four of the eight pins.
- RJ11: Called a type 11 registered jack, RJ11 has the capacity to be a six-pin connector. Most of them only have two or four conductors, and they are found in most home telephone networks which use just two of the six pins.
- DB-9 (RS-232): A nine-pin D-subminiature (DB-9) coiinnector is an older connector used for low-speed asynchronous communications such as to a serial printer, a router or switch, or an external modem. They look similar to DB-25 but are different.

![[Pasted image 20220828211935.png]]
