A wireless local area network is a LAN network made up of wireless networking devices. It is usually made with a wireless access point or a wireless router and requires the use of an antenna.

# Standards
Most WLAN standards are variations of the original IEEE 802.11 standard developed in 1997. That standards only supported speeds of up to 1 or 2Mbps, so it is outdated for today's bandwidth usage.

![[Pasted image 20220917161408.png]]

# Types
WLANs can be categorized based on their use of WAPs. The three main categories are independent basic service set (IBSS, also known as ad-hoc), basic service set (BSS), and extended services set (ESS).

### IBSS
IBSS, also known as ad-hoc, can be created without the use of an access point. It can be useful for transferring files between wireless devices.

![[Pasted image 20220917161847.png]]

### BSS
BSS uses just a single access point called a BSS WLAN. They are said to run in infrastructure mode because they connect wireless devices to a wired network infrastructure. It is often used in residential and SOHO locations, where a single access point is sufficient for all of the clients.

![[Pasted image 20220917162044.png]]

### ESS
ESS uses more than one access point and is called ESS WLAN. It also runs in infrastructuer mode, but supports more devices. It is important to prevent access points from overlapping. Specifically, nonoverlapping channels 1, 6, and 11 and the 2.4GHz band should be used.

![[Pasted image 20220917162251.png]]

# Interference
A major issue with WLAN is radio frequency interference (RFI) caused by other devices using similar frequencies to those of the WLAN devices. Physical obstacles can also impede or reflect transmissions.

- Other WLAN devices that don't use nonoverlapping channels
- Cordless phones that operate in the 2.4GHz band
- Microwave ovens, specifically older ones, can emit 2.4GHz signals
- Wireless security system devices usually operate in the 2.4GHz range
- Physical obstacles such as AC units or thick walls
- Signal strengths also impact the range

Most interference occurs in the 2.4GHz band as opposed to the 5GHz band, so the 5GHz band may be better for increased goodput (the number of useful information bits that the network can deliver).

# Security
The main approaches to WLAN security are MAC address filtering, disabling SSID broadcast, a preshared key, or IEEE 802.1X. There are also a few security standards, the most common of which are WEP, WPA, and WPA2.