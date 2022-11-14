Groups are organizational structures that are a part of Linux's discretionary access controls, or DAC. DAC is the traditional Linux security control where access to files, directories, and objects is based upon the user's identity and current group membership.

Groups are identified with their group identification number, or GID. This is similar to UIDs for user accounts.

# Viewing groups
To see the association between usernames, group names, and GIDs, there are a few commands that can be used:

- To find a username's GID: `getent passwd <username>`
- To find a username's group name: `groups <username>`
- To find a group name's GID: `getent group <group name>`
- To find a GID's group name: `grep <GID> /etc/group`

To list all groups, there are a few commands you can use depending on the amount of detail you want.

- To list all groups and details: `cat /etc/passwd`
- Alternatively: `getent passwd`

# Creating groups
The first group is created when a user account is created. This new group has the same name as the user account's name, and it is assigned a new GID.

To create a new group, use the `groupadd` command:

`groupadd <group name>`

You can use the `-g` flag to set a custom GID.

# Editing groups
To edit a group, use the `groupmod` command, similar to the `usermod` command. For example, to change a group's GID, you use the `-g` flag:

`groupmod -g <new GID> <group name>`

And to change a group's name, use the `-n` flag:

`groupmod -n <new group name> <old group name>`

# Editing user group membership
To add a user to a group, the `usermod` command is used:

`usermod <group name> <username>`

The `-aG` flag, if added, will retain any previous groups that the user is a part of.

# Deleting groups
Deleting groups is simple with the `groupdel` command:

`groupdel <group name>`