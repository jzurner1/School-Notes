A table on a [[Firewall|firewall]] that stores information about the current connections.

When a packet arrives at a firewall, the firewall checks the packet's header to determine if it is allowed based on the [[Access control list (networks)|access control list]]. If it is, an entry is added to the state table with information about the newly created connection. This entry includes things like the source and destination IP addresses, port numbers, and so on.

Connectionless protocols such as HTTP are inspected based on their header, but are not added to the state table. Some firewalls use application-layer inspection to make sure that the packets are constructed properly and don't contain any unexpected values.