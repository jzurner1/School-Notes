There are five main pieces of information you need to configure in a Linux system to let it interact on a network:
- The host address
- The network subnet address
- The default router (default gateway)
- The system hostname
- A DNS server address

There are three ways to configure this information:
- Manually editing network configuration files
- Using a graphical tool included with your Linux distribution
- Using command line tools


# Configuration files
Configuration files are located in different places for different distributions.
- Debian based is in `/etc/network/interfaces` file
- Red Hat based is in `/etc/sysconfig/network-scripts` directory
- openSUSE is in `/etc/sysconfig/network` file

### Debian
In Debian, the file will look something like this:
![[Pasted image 20221027172748.png]]
To use DHCP instead, the following would be used:
![[Pasted image 20221027172816.png]]

### Red Hat
There are two files used for each interface. The first one is named after the network interface, for example `ifcfg-eth0` or `ifcfg-lo`, and the second one is named `network`. The first file has most of the information while the second file has a couple important things such as the hostname and default gateway.

## DNS Server
Unlike the configuration file, all Linux systems have their DNS server file in one place. It is located in the `/etc/resolv.conf` file.

# Command line tools
There are two tools used for the command line, `nmtui` and `nmcli`. Both of them provide guidance through the process.

# Legacy command line tools
Sometimes the normal command line tools won't work so you need to use something else. The main five tools are `ethtool`, `ifconfig`, `ip`, `iwconfig`, and `route`.

### Ethtool
Ethtool lets you look inside NIC Ethernet settings and change any properties. By default, the command `ethtool <interface name>` will show you the current configuration settings for the network interface.

### Ifconfig
Ifconfig is a command used to set the network address and subnet mask for a network interface. It has been replaced with `ip addr` and `ip link`.

### IP
The IP command is a very popular method for command line settings. It has several options:
![[Pasted image 20221027180348.png]]
Each command uses parameters to define what to do such as displaying network settings or modifying existing settings.