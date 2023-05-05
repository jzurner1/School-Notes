The Linux file system is based on the Filesystem Hierarchy Standard. It is different than Windows and more similar to Mac.

### Everything is a file
What makes Linux unique is that literally everything is a file. Devices, settings, commands, and so on are all files stored somewhere in the filesystem.

For example, the `/bin` directory contains the `ls` command in the form of a file. According to the `file` command, it is an "ELF 64-bit LSB executable."

# Mount points
A mount point is a point in a filesystem where another filesystem is attached.

![[Pasted image 20221102110103.png]]

For example, in the image above, the root directory is on one partition or drive while the home directory is on another. This is a somewhat common setup.

# File paths
One of the most noticeable differences between Linux and Windows is the file paths:
- Windows: `C:\Users\Bob\Documents\Text.txt`
- Linux: `/home/Bob/Documents/Text.txt`
This is because of how the directories are laid out. In Linux, files can always be traced back to the root directory regardless of what drive they are on thanks to mount points. In Windows, files can be stored on different drives and thus their paths can have different starting points.

In Linux, there are two types of file paths:
- Absolute path, meaning it starts at root: `/home/Bob/Documents/Text.txt`
- Relative path, meaning it starts at the current location: `Text.txt`
If a doesn't start with a forward slash, Linux assumes that it is relative to the current directory.

# Tools
There are a number of tools for various goals within the Linux filesystem:

### ext filesystems
- **blkid**: Displays information about block devices such as storage drives
- **chattr**: Changes file attributes on the filesystem
- **debugfs**: Manually view and modify the filesystem structure, such as undeleting a file or extracting a corrupted file
- **dumpe2fs**: Display block and superblock group information
- **e2label**: Change the label on a filesystem
- **resize2fs**: Expand or shrink a filesystem
- **tune2fs**: Modify filesystem parameters

### XFS filesystem
- **xfs_admin**: Display or change filesystem parameters such as the label or UUID
- **xfs_info**: Display information about a mounted filesystem, including block and sector sizes as well as label and UUID information
- **xfs_repair**: Repair an XFS filesystem