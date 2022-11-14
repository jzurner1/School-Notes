The basic system of permissions for Linux has the major drawback in that you can only assign permissions for a file or directory to a single group or user account. This doesn't work too well in complex business environments.

As an alternative, an access control list will allow you to specify a list of multiple users or groups and the permissions assigned to them. They use the same rwx permissions as regular files and directory permissions.

You can use the command getfacl to view a file's access control list, and setfacl to change it.