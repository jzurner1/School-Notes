A routing protocol is a protocol that advertises route information between routers. It is important to distinguish between this and a routed protocol.

# Characteristics
This section looks at routing protocol characteristics used to decide on routes. Different routing protocols use different characteristics to make decisions.

### Believability
If a network is running more than one routing protocol (uncommon but possible) and a router receives two route advertisements from different routing protocols for the same network, it has to make a choice. Some routing protocols are considered more "trustworthy" than others. It is measured in administrative distance, or AD. Below is a table, where a lower number is more believable:

| Routing information source    | AD value |
| ----------------------------- | -------- |
| Directly connected network    | 0        |
| Statically configured network | 1        |
| EIGRP                         | 90       |
| OSPF                          | 110      |
| RIP                           | 120      |
| External EIGRP                | 170      |
| Unknown or unbelievable       | 255 (considered unreachable)         |

### Metrics
Some networks are reachable through more than one path. Choosing which route to take depends on the routing protocol what that routing protocol uses as a metric, or a value assigned to a route. Lower metrics are preferred to higher metrics. Some protocols prefer load balancing, while others prefer speed, and so on.

### Interior versus exterior gateway protocols
Routing protocols can be categorized based on the scope of their operation. Interior gateway protocols (IGPs) operate within an autonomous system, where an autonomous system is a network under a single adminstrative control. Conversely, exterior gateway protocols (EGPs) operate between autonomous systems.

![[Pasted image 20220913100013.png]]

In the image above, routers R1 and R2 are in one autonomous system (AS 65002) and routers R3 and R4 are in another autonomous system (AS 65003). Between R1 and R2 and IGP is used to exchange routing information, and the same is true for R3 and R4. However, ISP1 is on a separate autonomous system (AS 65001) that is run by a service provider. An EGP (typically border gateway protocol or BGP) is used to exchange routing information between different autonomous systems such as AS 65001 and AS 65002.

### Route advertisement method
Another characteristic of a routing protocol is how it receives, advertises, and stores routing information. The two fundamental approaches are distance vector and link state.

##### Distance vector
A distance-vector routing protocol sends a full copy of its routing table to its directly attached neighbors. It is sent at regular intervals even if there have been no changes to the network; this is inefficient and ideally it would only be sent when changes occur.

Another drawback is that it takes more time for them to converge, meaning the rime required for all routers to update their routing tables in response to a network change. One more issue is the potential of a routing loop.

##### Link state
Rather than having neighboring routers exchange their full routing tables with one another, a link-state routing protocol allows routers to build a topological map of the network and execute an algorithm to calculate an optimal path to a destination network.

Routers send link-state advertisements (LSAs) to advertise the networks they know how to reach. Routers than use those LSAs to construct the topological map of a network. It uses the Dijkstra's shortest path first algorithm.

Unlike distance-vector routing protocols, link-state routing protocols exchange full routing information only when two routers initially form their adjacency. Routing updates are then only sent in response to changes in the network, making it more efficient than being sent periodically. Also, link-state routing protocols benefit from shorter convergence times than distance-vector routing protocols.

# Protocols list
This section lists some of the most popular routing protocols used in modern networks:

### Routing information protocol (RIP)
RIP is a distance-vector protocol that uses the metric hop count. The maximum number of hops between two routers in an RIP-based network is 15. It is an IGP.

### Open shortest path first (OSPF)
OSPF is a link-state routing protocol that uses the metric cost, which is based on the link speed between two routers. It is a popular IGP because of its scalability, fast convergence, and vendor interoperability.

### Intermediate system-to-intermediate system (IS-IS)
IS-IS is an IGP similar to OSPF, but it is not as widely deployed.

### Enhanced interior gateway routing protocol (EIGRP)
EIGRP is a Cisco-proprietary protocol that is popular in Cisco-only networks but not as popular in others. It is an IGP similar to OSPF and is sort of a combination of distance-vector and link-state routing protocols. It uses bandwidth and delay in its metric calculation but other metrics such as reliability, load, and MTU can be considered.

Some books call EIGRP an advanced distance-vector routing protocol while others call it a hybrid routing protocol. It uses information from its neighbors to help select an optimal route but it also maintains a database of topological information. It does not use Dijkstra's shortest path first algorithm, rather it uses diffusing update algorithm (DUAL).

### Border gateway protocol (BGP)
BGP is the only EGP in widespread use today. It is considered to be the routing protocol that runs the internet. It is most accurately described as a path-vector routing protocol, meaning that it can use as its metric the number of autonomous system hops that must be transited to reach a destination network as opposed to a number of required router hops.

BGP's path selection is not solely based on autonomous system hops, however. BGP can consider a variety of other parameters, but none of them are based on link speed. In addition, while it is incredibly scalable, it does not converge quickly in the event of a topological change.

### Table
The following table compares the key characteristics of dynamic routing protocols. It only lists the DRPs that are certain to appear on the Network+ exam:

| Routing protocol | IGP/EGP | Type            | Metric                                     |
| ---------------- | ------- | --------------- | ------------------------------------------ |
| RIP              | IGP     | Distance vector | Hop count                                  |
| OSPF             | IGP     | Link state      | Cost of bandwidth                          |
| EIGRP            | IGP     | Hybrid          | Composite (bandwidth and delay by default) |
| BGP              | EGP     | Path vector     | Path attributes                                           |
