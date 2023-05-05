Neighbor discovery protocol, the protocol used for network discovery in IPv6

It defines five IMCPv6 packet types for important jobs:
- Router solicitation: A network host will send a router solicitation message to locate routers on an attached link
- Router advertisement: Routers advertise their presence with various link and internet parameters, either periodically or in response to a router solicitation message
- Neighbor solicitation: Used by network nodes to determine the link layer address of a neighbor or to verify that a neighbor is still reachable
- Neighbor advertisement: Used by nodes to respond to a neighbor solicitation message
- Redirect: Routers may inform hosts of a better first-hop router for a destination