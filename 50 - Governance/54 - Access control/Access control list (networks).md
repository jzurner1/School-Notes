Network access control lists (ACLs) are lists attached to devices (such as routers or switches) that specify what type of traffic is allowed through. Inbound and outbound rules are typically on separate ACLs.

The purpose of a network ACL is for packet filtering, one of the oldest and most common ways of restricting network traffic for security purposes. For example, you can block IP addresses that have attempted attacks against your network, or IP addresses that host known phishin sites.

The parameters of ACLs depend on the device, software, and purpose of the device. ACLs on devides on the edges of networks tend to focus on edge control, examining packet origins to restrict outside traffic. ACLs on interior devices tend to focus on core control, examining packet destinations to control or restrict their path through the network.

# Rules
An ACL is similar to a MAC table or routing table. When a router (or other device) receives a packet, it checks it against the ACL and applies whatever rule fits the situation. There are two basic models for rules:
- **Implicit deny**: Access is denied unless a rule explicitly allows it. An ACL with only explicit allowances is called a whitelist or allow list.
- **Implicit allow**: Access is allowed unless a rule explicitly denies it. An ACL with only explicit denials is called a blacklist or block list.

Implicit deny is harder to set up but it is the norm because it doesn't leave security holes if an entry is deleted or forgotten.