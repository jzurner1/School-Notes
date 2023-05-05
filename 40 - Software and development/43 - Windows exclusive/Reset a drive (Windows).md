Resetting a drive means entirely wiping it and resetting the partitions. This can be helpful if a drive is having issues and you don't care about the data on it.

1. Open the [[Disk Management|Disk Management]] tool
2. Find the drive you want to wipe and write down its drive number (eg. 4)
3. Open the command prompt
4. Enter `diskpart` to open the disk partition tool
5. Enter `select disk <drive number>` to select the disk you want to reset
6. Enter `clean` to delete all files and partitions
7. Enter `create partition primary` to create a main partition
8. Enter `active` to set that partition as the active partition
9. Enter `format fs=<drive format> quick` where drive format can be ntfs, fat32, etc.
10. After formatting, enter `exit` to finish