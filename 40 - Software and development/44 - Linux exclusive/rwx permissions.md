Read, write, execute permissions are used in Linux to show what permissions are relevant to a given file.

To see the rwx permissions of a file, you can run `ls -l <filename>`. It will print out something like this:
`-rwxrw-r-- 1 ubuntu01 ubuntu01 44 Nov 2 22:12 testfile.txt`
The most important part of that is the first ten slots.

The very first entry represents the filetype. In this case, a dash indicates a plain file. A `d` would indicate a directory.

The next nine entries represent the permissions. The first three characters are for the User class, meaning the file owner. The next three characters are for the Group class, meaning the group that owns the file. The last three define permissions for the Others class, meaning any user that isn't the owner or in the group that owns the files.

In the example above, the nine entries are `rw-rw-r--`. The first three, `rw-`, give the owner the ability to read and write the file; they can't execute it because it's a text file. The next three, `rw-`, follow the same pattern but for the group that owns it. The last three, `r--`, indicate that other users can read the file but can't write to it.

# Numerical permissions
As an alternative to the `rwx` format, numbers can be used. There are four number slots and they are most often used with the chmod command. The first slot is optional for a special flag, and the other three represent the user class, group class, and others class.

Permissions can be from a 0 to 7 for each of the three slots. They each correspond to a specific rwx set. `r` means 4, `w` means 2, and `x` means 1. Add them up to get the appropriate numerical permission for each slot.

![[Pasted image 20221105115716.png]]

For example, changing a file's permission to `754` would mean:
- 7 for user class: read, write, and execute (4 + 2 + 1 = 7)
- 5 for group class: read and execute (4 + 0 + 1 = 5)
- 4 for others class: read only (4 + 0 + 0= 4)