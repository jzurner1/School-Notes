## Overview
A virtual local area network is a logical [[Subnet|subnetwork]] that groups together a collection of devices from different physical LANs. They are often used with larger businesses to partition a network for improved traffic management. It is supported with several kinds of physical networks such as Ethernet and WiFi.

For example, if you have a large business with different departments, you will want to put those departments into smaller subnets. This may mean having the accounting department in one subnet and the sales department in another. This can be done easily with VLANs.

## Creation
VLANs are created through VLAN-enabled [[Switch|switches]]. The ports on these switches can be configured to separate network traffic without using routers.

For example, if you have a business with a sales department, HR department, and service department, you may want to divide them but don't want to manually [[Subnet|Subnet]] them. To do this, certain ports on the switch can be configured to be a part of a VLAN. You may take four ports on the switch and configure them to be VLAN 1, then connect devices from the sales department to them. This can be repeated with two other VLANs for the other two departments.