A Linux server is simple a server running on a Linux operating system.
# Servers vs. Desktops
Linux servers and Linux desktops use the same Linux kernel, run the same shells, and have the ability to run the same programs. The biggest difference is which programs are primarily run and how they are run.

Unlike Linux desktops, Linux servers primarily operate without any human interaction. They run programs that provide shared resources (services) to multiple users (clients), usually in a network environment. Most services run all the time, even when they aren't being used.

They usually use command line interfaces instead of GUIs and often must be accessed with remote access.

# Launching services
There are two main ways that a Linux server can run services. The first is as a background process, running all the time and listening for requests (called a daemon), and the other way is as a process spawned by a parent program that listens for requests (called a super-server).

# Listening for clients
Both daemons and super-servers use separate network protocols to communicate with clients. Each of these protocols use different ports. The `/etc/services` file contains a list of all the ports defined.