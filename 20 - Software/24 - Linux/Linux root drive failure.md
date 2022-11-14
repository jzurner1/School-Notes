When the root drive can't load, it may be fatal for the entire system. There are ways to try and fix it, however.

### Using a rescue disk
Many Linux distributions provide a rescue disk for when fatal disk errors occur. The disk usually boots either from the CD drive or as a USB stick and loads a small Linux system into memory. Since the smaller system runs entirely in memory, it can leave the hard drives free for repair.

The tool of choice for checking and fixing hard drive errors is the `fsck` command, which is an alias for a family of commands specific to different types of filesystems such as ext2, ext3, and ext4. To do this, run the `fsck` command against the device name of the partition that contains the root directory: `fsck /dev/sda1`.

The `fsck` command will examine the inode table along with the file blocks stored on the hard drive and attempt to reconcile them. If any errors did occur, you can repair them. After errors are repaired, run the `fsck` command again to see if there are any more issues. Keep repeating until you get a `fsck` run with no errors.

### Mounting a root drive
After using `fsck`, you can test the repaired partition by mounting it into the virtual directory created in memory using the `mount` command to mount it to an available mount directory: `mount /dev/sda1 /media`. Examine to make it isn't corrupt, then unmount it before rebooting: `unmount /dev/sda1`