A virtual private cloud (VPC) isolates resources for an organization within a public cloud. In a VPC, you can do anything that you could do in a private cloud. VPCs combine the scalability and convenience of public clouds with the data isolation of private cloud computing, as some of the resources are reserved for use by the VPC customer.

Every cloud service provider has some form of VPC. For example, Microsoft Azure has Azure VNet.

### Isolation
There are a few ways that a VPC is isolated from the rest of the public cloud:
- **Subnets**: Subnets can be used to reserve a range of IP addresses for special use. For isolation, some of the private IP addresses of the cloud are reserved specifically for the VPC.
- **VLAN**: A VLAN is a virtual local area network. Similar to a subnet, it is a way of partitioning a network. Unlike subnets, partitioning takes place at layer 2 of the OSI model instead of layer 3.
- **VPN**: VPNs use encryption to create a private network that works on top of a public network. This can be used to communicate solely with the VPC.

### Advantages
- **Scalability**: Because a VPC is hosted by a public cloud provider, customers can add more computing resources on demand.
- **Easy hybrid cloud deployment**: It's simple to connect a VPC to a public cloud or on-premises infrastructure using a VPN, which forms a hybrid cloud.
- **Better performance**: Cloud-hosted websites and applications are usually faster than those hosted locally.
- **Better security**: The public cloud providers that offer VPCs usually have a lot of resources for updating and maintaining infrastructure. This is mostly true for small and medium businesses, but less so for large ones that require more security.