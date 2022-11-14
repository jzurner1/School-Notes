There are many types of filesystems in use today.

# Linux
- **btrfs**: A newer, high-performance filesystem that supports over 18 million terabytes of size. It can perform its own form of RAID as well as logical volume management (LVM). It includes additional advanced features such as built-in snapshots for backup, improved fault tolerance, and data compression on the fly.
- **eCryptfs**: The Enterprise Cryptographic File System (eCryptfs) applies a POSIX-compliant encryption protocol to data before storing it on the device. This provides a layer of protection for data stored on the device. Only the operating system that created the filesystem can read data from it.
- **ext3**: Also known as ext3fs, this is a descendant of the original Linux filesystem. It supports file systems up to 16TB in size. It supports journaling and utilizes improved performance features.
- **ext4**: Also known as ext4fs, this is the current version of the original Linux filesystem. It supports file systems up to 1 million terabytes in size. It also supports journaling and utilizes improved performance features.
- **reiserFS**: Created before ext3 and commonly used on older Linux systems, it provides features now found in ext3 and ext4. Linux has dropped support for the most recent version, reiser4fs.
- **swap**: The swap filesystem allows you to create virtual memory for your system using space on a physical drive. The system can then swap data out of normal memory into the swap space, providing a method of adding additional memory to your system.


# Linux-supported
- **CIFS**: The Common Internet File System (CIFS) was created by Microsoft for reading and writing data across a network using a network storage device. It was designed to be used on all operating systems.
- **HFS**: The Hierarchical File System (HFS) was developed by Apple for its Mac OS systems. Linux can also interact with the more advanced HFS+.
- **ISO-9660**: Used for creating filesystems on CD-ROM devices.
- **NFS**: The Network File System (NFS) is an open-source standard for reading and writing data across a network using a network storage device.
- **NTFS**: The New Technology File System (NTFS) is the filesystem used by the Microsoft NT operating system and subsequent versions of Windows.
- **SMB**: The Server Message Block (SMB) filesystem was created by Microsoft as a proprietary filesystem used for network storage and interacting with other network devices. It allows Linux clients and servers to interact with Microsoft clients and servers on a network.
- **UDF**: The Universal Disc Format (UDF) filesystem is commonly used on DVD-ROM devices for storing data. Linux can both read and write data to a DVD using this.
- **VFAT**: The Virtual File Allocation Table (VFAT) is an extension of the original Microsoft FAT filesystem. It's not commonly used on drives but is common for removable storage devices such as USB sticks.
- **XFS**: The X File System (XFS) was created by Silicon Graphics for its now-defunct workstations. It has some high-performance features that make it still relatively popular in Linux.
- **ZFS**: The Zettabyte File System (ZFS) was created by a subsidiary of Oracle for use with their Unix workstations and servers. It has features similar to btrfs.


# Windows
- **CDFS**: Used for optical media
- **FAT**: Also called FAT16, used with all versions of Windows. 2GB partition limitation on older OSes and 4GB limit on XP and higher
- **FAT32**: Supported by all Windows versions. Supports drives up to 2TB; can recognize volumes greater than 32GB but cannot create them
- **exFAT**: Also called FAT64, made for removable media. 512TB is the recommended max. Made for copying large files such as disk images and media. Supported by all Windows versions