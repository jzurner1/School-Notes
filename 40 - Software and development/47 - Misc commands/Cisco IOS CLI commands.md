Commands for the [[Cisco IOS CLI|Cisco IOS CLI]]

- `?` - Show help for all available commands
- `<command> ?` - Describe all first parameter options for the command`
- `<com>?` - List all commands that start with `<com>`
- `clear mac address-table dynamic` - Remove all dynamic entries from the MAC table
- `clear mac address-table dynamic address <mac>` - Remove an entry from the MAC table based on a MAC address
- `clear mac addreess-table dynamic interface <name>` - Remove an entry from the MAC table based on an interface name
- `clear mac address-table dynamic vlan <num>` - Remove all the entries from a MAC table that are on a particular VLAN
- `configure terminal` - Enter configuration mode (must be in enabled mode)
- `debug` - Similar to `show` but shows a live version
- `disable` - Switch to user EXEC mode
- `enable` - Switch to enabled mode, also known as privileged EXEC mode
- `enable secret <value>` - Set a password for enable mode
- `hostname <name>` - Change the device's name; must be in configuration mode
- `interface <interface type and number>` - Enter configuration mode for an interface
- `ip address <ip address> <mask>` - Assign an IP address and subnet mask
- `ip default-gateway <ip address>` - Set a device's default gateway
- `login` - Enable the use of a password; use `password` next
- `password <value>` - Set a password; must use `login` beforehand; not for enable password
- `reload` - Reboot a device (must be in enabled mode)
- `show` - Combined with an option, gives the status of a certain feature or object
- `show history` - List the commands currently held in the history buffer
- `show interfaces <name> counters` - Show statistics about incoming and outgoing frames
- `show interfaces status` - Show the status of each interface
- `show mac address-table` - Show the MAC address table
- `show mac address-table aging-time` - Show the default [[Switch#Aging|aging time]] for MAC table entries
- `show mac address-table dynamic` - Show dynamically learned MAC addresses
- `show mac address-table dynamic address <MAC>` - Show an individual device based on a MAC address
- `show mac address-table dynamic interface <name>` - Show an individual device based on an interface name (full name, such as `fastEthernet 0/1`)
- `show mac address-table dynamic vlan <num>` - Show all the devices on a particular [[VLAN|VLAN]]
- `show running-config` - Show the device's current configuration