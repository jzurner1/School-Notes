A type of attack that takes advantage of Q-in-Q tunneling, an approach that involves encapsulating 802.1Q traffic inside other 802.1Q traffic.

The exploit uses the combination of Q-in-Q tunneling and the native VLAN feature to send traffic into a VLAN that an attacker would not normally be able to send traffic into. This is called VLAN hopping.

Common security changes to prevent VLAN hopping attacks include ensuring that the native VLAN is set toa completely unused VLAN or, for switches that support it, tagging the native VLAN.