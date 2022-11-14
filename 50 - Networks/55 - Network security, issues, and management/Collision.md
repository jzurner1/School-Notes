A collision occurs on a network when two devices send data at the same time and it occupies the same network segment. This can cause data corruption.

With Ethernet, a back-ff timer is set after a collision to prevent future collisions.

# Collision domains
A collision domain is a group of devices with the potential to collide. For example, if a few devices are on a single bus network, they have the potential to collide on the main wire and thus are all in a collision domain.

In addition, devices that are on an Ethernet hub are in the same collision domain. This is because a hub is a layer 1 devices and does not make forwarding decisions; instead, bits are taken in one port and sent out of all other ports.

Ethernet switches increaase the scalability of an Ethernet network by creating multiple collisions domains, because each port on an Ethernet switch is in its own collision domain.