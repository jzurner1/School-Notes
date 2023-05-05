Uptime/availability is a very important consideration when designing a network.

Availability is measured by its uptime during a year, measured in percent. Generally, a network will be available 99.9999% or so percent of the time, and that is called six nines availability. The same applies for three nines, five nines, and so on. The more nines there are, the better.

# Vocabulary
There are a lot of important terms and technologies that have to do with availability:

### Availability
Whether or not a network is up and operational

### Reliable
Whether or not a network drops many packets

### MTTR
Mean time to repair, the average amount of time required to fix a failed component and return it to production status

### MTBF
Mean time between failures, the average amount of time that passes between hardware component failures, excluding time spent repairing components

### MTTF
Mean time to failure, how long a device is expected to last in operation

### RTO
Recovery time objective, the time in the future when you expect to restore availability after it is lost

### RPO
Recovery pooint objective, the point in time in which you can recover the network, measured in the amount of time lost. For example, if a network fails at 11PM and you can recover data up to 8PM, that is 2 hours lost.

### Fault-tolerant network
A network that is designed to be able to work even in the event of an obstacle such as a security breach, power loss, or disaster.

### Single point of failure
A single point in a network that, if it fails, could cause the rest of the network to fail. This may be a connection between a router and its power outlet, an Ethernet cord between two major parts of the network, and so on.

### Redundancy
Repeated pieces of hardware or software used to prevent a single point of failure. This may mean a source of backup power, two cords between devices, and so on.

### NIC redundancy
Redundancy for a NIC. There are two ways to do it. The first (active-active) has both NICs active at the same time and each has its own MAC address; troubleshooting is more complicated but there is slightly better performance. The second (active-passive) only has one NIC active at a time, allowing the client to appear to have a single MAC and IP address

### Computer cluster
A group of computers connected with very fast LANs, often viewed as a single system. Each computer has its own hardware and operating system, but it is usually the same type for each.

### Layer 3 redundancy
Devices without a routing protocol will point to a default gateway, usually the subnet's router. If, however, the default gateway fails, the devices will be unable to leave the subnet. This introduces First Hop Redundancy Protocols (FHRPs), of which there are four (HSRP, CARP, VRRP, and GLBP). Each of those FHRPs effectively works with a backup router that can work as the default gateway.

### Content engine
A network appliance that can receive a copy of content stored somewhere else, such as on another server, and serve it to local clients, reducing the bandwidth burden on an IP WAN.