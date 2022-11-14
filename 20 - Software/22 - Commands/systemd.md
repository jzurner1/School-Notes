systemd is a software suite for Linux systems that aims to unify service configuration and behaviors across Linux distributions. Its main component is a system and service manager, which is an init system used to manage user processes, among other things. It also provides replacements for various daemons and utilities include device management, login management, network connection management, and logging.

# Unit files
A systemd unit is a service, group of services, or an action. Each unit consists of a name, a type, and a configuration file. There are 12 different systemd unit types. They are automount, device, mount, path, scope, service, slice, snapshot, socket, swap, target, and timer.

The systemctl command utility is the main way to manage systemd and system services. Its syntax is `systemctl <options> <command> <name>`.

One useful command is `systemctl list-units`, which will print all units. The columns it will print are UNIT, LOAD, ACTIVE, SUB, and DESCRIPTION.
- UNIT is the name of the unit combined with the type in the format `name.type`, such as `sshd.service`, the ssh daemon.
- LOAD is if the service has been parsed by systemd. The configuration of the loaded units is kept in memory.
- ACTIVE will say whether or not the unit has started successfully.
- SUB gives more details about the unit, but it shows different information for different units.
- DESCRIPTION is a short description of what the unit is and does.

Groups of services are started with **target** unit files. such as `network.target`. At system startup, the `default.target` unit is responsible for ensuring that all required and desired services are launched at system initialization.