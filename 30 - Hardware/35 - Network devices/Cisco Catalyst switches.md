Cisco Catalyst switches are Cisco's brand of LAN switches. Within this brand, there are a number of switch series/families, where each series includies several specific models of switches that have similar features, prices, performance, and internal components.

They use the [[Cisco IOS CLI|IOS CLI]] for commands.

## Defaults
Cisco Catalyst switches are ready out of the box. They just have to be plugged in, powered on, and connected to switches.

By default, they have the following settings:
- The interfaces are all enabled by default, ready to start working once they receive a cable
- All interfaces are assigned to VLAN 1
- 10/100 and 10/100/1000 interfaces use autonegotiation by default
- The MAC learning, forwarding, and flooding logic all work by default
- [[STP|STP]] is enabled by default

## Port naming scheme
Each port has both an interface type and interface number.

The interface type can be Ethernet (10Mbps), Fast Ethernet (100Mbps), Gigabit Ethernet (1000Mbps), and so on for faster speeds. For interfaces that support multiple speeds, the name of the fastest supported speed is used.

The interface number is two digits (x/y) on older devices and three digits (x/y/z) on newer devices. For example, two 1000 ports on an old switch may be called GigabitEthernet 0/0 and GigabitEthernet 0/1 while two 1000 ports on a new switch may be called GigabitEthernet 1/0/1 and GigabitEthernet 1/0/2.

There are also shortened versions. For example, GigabitEthernet0/1 may be called Gi0/1, and FastEthernet0/2 may be called Fa0/2.