# Hard links
A hard link is a file or directory that has one index (inode) number but at least two different file names. Because they both have only one inode number, they are a single file on the filesystem.

![[Pasted image 20221017174816.png]]

In the image above, if filename #1 is edited, those edits will be written to the disk and filename #2 will be edited as well. The same is true if you edit filename #2, because they are just different names for the same file. These filenames can exist in different directories but must exist in the same filesystem.

A hard link allows you to have a pseudo-copy of a file without truly copying the data. This is used in file backups when not enough filesystem space exists to back up the file's data; if one of the file's names is deleted, you will still have another file name that links to the data.

The command to create a file link is `ln file1 file2`, where `file1` already exists and `file2` does not.

# Soft links
A soft link provides a pointer to a file that already exists. They do not share inode numbers.

![[Pasted image 20221017175639.png]]

There are a few differences between a soft link and a hard link. For one, the files do not share inode numbers and they do not share the same data. However, if you edit one, the other one will still change.

To remove a link, do `unlink <filename>`