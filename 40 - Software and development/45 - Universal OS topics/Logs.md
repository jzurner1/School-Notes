A log is a record of events for a particular thing, depending on the type of log.

# Traffic logs
Traffic logs detail traffic statistics for key areas of a network's infrastructure. There are many forms of traffic logging mechanisms, and many of them are built into devices. NetFlow is a very popular example of this.

# Audit logs
Audit logs contain records of actions that were performed in a network. For example, this may contain accounts that attempted to access a network resource. AWS offers a tool called CloudTrail that logs every activity in its public cloud environment.

# Syslog
A number of network devices send their information to a common syslog server. By having information for multiple devices in a common log and examining time stamps, network administrators can better correlate events on multiple devices. Syslog messages combined with SNMP traps can be used to trigger notifications via email or SMS. There are two primary components of a syslog logging solution:

### Syslog server
A syslog server recieves and stores log messages sent from syslog clients.

### Syslog clients
Various types of network devices can act as syslog clients and send logging information to a syslog server, as seen below.

![[Pasted image 20220918135252.png]]

### Messages
Messages sent from a syslog client to a syslog server vary in their severity levels. The higher the level, the more detailed the log. More detailed logs require more space on the system:

![[Pasted image 20220918135415.png]]

Syslog messages contain time stamps, priority, date, host, and the actual message, as seen below.

![[Pasted image 20220918135518.png]]

# OS logs
In addition to logs generated by routers, switches, and other devices, the operating system powering network clients and servers can generally produce log output. Rather than general log information, Microsoft Windows uses the event viewer application, which allows you to view various log types including application, security, and system logs. These logs can be archived for later review and used to spot network trends.

# Application logs
Microsoft Windows application logs contain information about software applications running on the underlying operating system. In the image below, the collection of logs provides a collection of information about events:

![[Pasted image 20220918135845.png]]
