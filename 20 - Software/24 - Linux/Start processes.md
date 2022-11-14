A start process is the first programs run as a Linux machine starts up. This occurs immediately after the boot processes finishes, now in the final system initialization stage.

# init
Init was one of the first start processes, but it has since become less popular. In essence, there are different runlevels and the `/etc/inittab` file will point the system to which scripts to run for each runlevel. Scripts can be found in `/etc/init.d/rc`, followed by a number for each runlevel.

Each runlevel has a directory of scripts. When entering the runlevel, the scripts will start with an `s`. When exiting the runlevel, the scripts will start with a `k`.

# systemd
Systemd introduced a number of changes to the start process. Services can be started on boot, when a particular hardware component is attached to the system, when other services are started, and so on. They can also start based on a timer.