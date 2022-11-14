The `systemctl` command utility is used to manage systemd and system services.

Its syntax is `systemctl [options] <command> [name]`

One useful command is `systemctl list-units`, which will print all units. The columns it will print are UNIT, LOAD, ACTIVE, SUB, and DESCRIPTION.
- UNIT is the name of the unit combined with the type in the format `name.type`, such as `sshd.service`, the ssh daemon.
- LOAD is if the service has been parsed by systemd. The configuration of the loaded units is kept in memory.
- ACTIVE will say whether or not the unit has started successfully.
- SUB gives more details about the unit, but it shows different information for different units.
- DESCRIPTION is a short description of what the unit is and does.

Another useful command is `systemctl status <process>`, which will show the current status of a process. For example, to see the status of the SSH daemon, you can do `systemctl status sshd`.

To start a process, you can do `systemctl start <process>`. To stop a process, just do `systemctl stop <process>`.