Routing is the process of selecting a path for traffic in a network or between or across multiple networks.

# Routing table
A routing table is used to find best matches when routing an IP packet. The best match is the route that has the longest prefix, meaning the most specific network. For example, if a router has an entry for 10.0.0.0/8 and 10.1.1.0/24 and is looking for the destination 10.1.1.1/24, the router would choose 10.1.1.0/24 as it has the longest prefix (/8 versus /24).

# Directly connected routes
A router that has an interface directly participating in a network knows how to reach that specific destination network.

![[Pasted image 20220912171351.png]]

In the above image, router R1 knows how to reach the networks 192.168.1.0/24 and 192.168.2.0/30 because it has an interface in both of these networks. Router R2 has an interface in the networks 192.168.2.0/30 and 10.1.1.0/30 and thus can reach them. These entries are known as directly connected routes because they are directly connected.

# Static routes
Static routes are routes that are statically configured in a router's routing table. In the previous example, router R1 needs to send any internet traffic to R2 because it is the next hop on the network. Specifically, R1 could be configured with a default static route that says "if traffic is destined for a network not currently in the routing table, send that traffic out of interface Serial 1/1."

# Dynamic routing protocols
In larger networks, static routing does not scale well. There are a lot of dynamic routing protocols that fortunately allow a router's routing table to be updated as network conditions change.

![[Pasted image 20220912173614.png]]

In the image above, router R2 is advertising a default route to its neighbors R1, R3, and R4. If PC1 wants to send traffic to the internet, it may be difficult. R3 is PC1's default gateway, and R3 has three default routes.

R3's routing decision based on the routing protocol being used. A routing protocol such as routing information protocol (RIP) would make the path selection based on the number of routers that must be used to reach the internet (the hop count) and would thus choost the 128Kbps link to R2. This isn't the fastest link, but RIP doesn't consider speed.

Dynamic routes also allow a router to reroute around a failed link. For example, if R4 was the selected method and it failed, the route would change to a different router such as R1. The process of choosing a backup route is called convergence.