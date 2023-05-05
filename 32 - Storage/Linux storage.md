In [[Linux|Linux]], [[Storage|Storage]] is handled a bit differently than other operating systems.

Related commands: `df`, `du`, `iostat`, `lsblk`

# Drives
Drives are named in order of their detecting. The first drive is `/dev/sda`, the second `/dev/sdb`, and so on. Partitions are named by appending numbers to the end of their appropriate drives; partitions on the drive `/dev/sdb` would be called `/dev/sdb0`, `/dev/sdb1`, and so on.

### Mounting
When a drive is first connected to a Linux system, if it doesn't automatically mount, you need to do it yourself. This assumes that the drive is already partitioned.

The command `lsblk`, by itself, will list out all of the block devices on a system. This includes both mounted and unmounted drives. It will show the sizes, type, and mount points for the drives.

Before actually mounting the device, you need a location to mount it to. This is usually done by creating a subfolder under the `/mnt` directory. For example, you may want to do `mkdir /mnt/newdrive`.

The `mount` command is used to actually mount a device. When mounting a device, make sure you specify the partition to be mounted, not just the device itself (i.e. you would mount `sdb0`, not `sdb`). The command is just `mount /dev/<device name> <mount location>`, for example `mount /dev/sdb1 /mnt/newdrive`.

When mounting a device, you can specify the filesystem with the `-t` flag.

### Unmounting
Unmounting a device should be done before removing it from a filesystem. The command is simply `umount <mount location>`. Again, the mount location can be found with the `lsblk` command. For example, you may do `umount /mnt/newdrive`.

# Partitioning
The following assumes that your Linux system uses the more modern GUID Partition Table (GPT) to manage partitions.

### fdisk
`fdisk` is the most common command-line partitioning tool. It allows you to create, view, delete, and modify partitions on any drive that uses the MBR method of indexing partitions.

To use `fdisk`, you enter `fdisk <drive name>`. This will open a command line that takes in commands specially for drives:

![[Pasted image 20221101180307.png]]

### gdisk
`gdisk` is similar to `fdisk` except it is for drives with the GPT indexing method:

![[Pasted image 20221101180428.png]]

### parted
The `parted` command is another tool to work with drive partitions. It is especially useful because it lets you modify existing partition sizes.

# Automatic drive detection
Most Linux systems use the udev program, which runs in the background all the time and automatically detects new hardware connected to the running Linux system. Each of them will be added to the `/dev` folder with their appropriate new name.

Because removable drives can be attached and removed often, the file system needs to be able to recognize them. To solve this, the udev application uses the `/dev/disk` folder to create links to the `/dev` storage device files based on unique attributes of the drive. There are four separate folders udev creates for storing links:

- `/dev/disk/by-id` links storage devices by their manufacturer make, model, and serial number
- `/dev/disk/by-label` links storage devices by the label assigned to them
- `/dev/disk/by-path` links storage devices by the physical hardware port they are connected to
- `/dev/disk/by-uuid` links storage devices by the 128-bit UUID assigned to the device