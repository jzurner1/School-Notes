Running a local network requires a number of local resources to keep clients and servers in sync. Linux servers can be set up to assist in this in a number of ways.

# Network resources
### IP addresses
Every device on a local network needs to have an IP address set up to interact with other devices on the network. On larger networks, DHCP servers can be used to provide valid IP addresses and keep track of them to ensure that no two clients have the same IP address.

### Logging
In normal Linux systems, logging files are held in the `/var/log` directory. In a network environment, it can be useful to store logs on a remote logging server instead. This provides a safe backup of the original log files plus a safe place to store logs.

The two main logging packages used in Linux are rsyslogd and journald. rsyslogd is used by the SysVinit and Upstart systems to accept logging data from remote servers, while journald is used by the Systemd system for both local and remote logging of system information. Both of them utilize configuration files to allow you to define how the data is logged and what clients the server accepts log messages from.

### Network management
The simple network management protocol provides a way for administrators to query remote network devices and servers to obtain information about their configuration, status, and performance. The most popular SNMP software package in Linux is net-snmp.

### Time
The network time protocol is a protocol that allows servers and clients to synchronize on the same time source across one or multiple networks, adding or subtracting fractions of a second as needed to stay in sync. For Linux, the ntpd program synchronizes the system with remote NTP servers on the internet. Usually, a single local server will use ntpd and all other servers and clients will sync with that server.

# Security
### Authentication server

### Access server (SSH)
Secure shell (SSH) provides a secure way to remotely access a server. The most popular Linux implementation iss OpenSSH.

### VPN server
A VPN allows you to securely connect to a server from your local network through the internet. The VPN protocol creates a secure point-to-point tunnel between a remote client or server and a VPN server on your local network. The most most popular Linux solution is the OpenVPN package.

### Proxy server
A web proxy server allows you to intercept web requests from local network clients. By intercepting the web requests, you can control how clients interact with remote web servers. You can block certain websites and cache common websites for future requests. The most popular Linux implementation is the Squid package, which can be configured as a filter and a chaching server.

# Performance

### Clustering

### Load balancing