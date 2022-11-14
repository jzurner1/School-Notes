Defense in depth is a security concepts that involves striving to secure each layer of a solution.

For example, you might use strong security on containers and virtual machines that provide SaaS, then strong security controls for the host systems. Next, add strong security controls on the network switch. Keep adding layers until each layer is secured.

# Approaches
There are a number of techniques that should be used with defense in depth to make it work fully.

### Network segmentation enforcement
The logical segmentation of networks used to enforce strong security designs. For example, VLANs can be used to constrain broadcasts and permit the definition of VLAN access control lists (ACLs) and router ACLs for controlling communication between VLANs.

Network segmentation enforcement can also help to minimize the effects of security attacks by limiting them to the local subnet.

### Screened subnet
A screened subnet, previously called a demilitarized zone (DMZ), often contains servers that should be accessible from the public internet.