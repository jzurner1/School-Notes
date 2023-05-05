A backup, also known as an archive, is a copy of data that can be restored sometime in the future, generally if the original data is destroyed or corrupted.

### System image
A system image is a copy of the operating system binaries, configuration files, and anything else needed to boot the system. Its purpose is to quickly restore your system to a bootable state. Also known as clones, these backups are not normally used to recoved individual files or directories.

### Full
A full backup is a copy of all the data on a system, ignoring its modification date. This backup type takes a lot less time than others to restore all of a system's data, but it takes longer to create a backup and requires more storage.

### Incremental
An incremental backup only makes a copy of data that has been modified since the last backup of any type. This is usually done by comparing a file's last modified timestamp to the last backup's timestamp. This is quicker to create than other types and requires less storage space, but data restoration will take a lot longer.

### Differential
A differential backup makes a backup of all data that has changed since the last backup. It is a good balance between full backups and incremental backups, and it takes a moderate amount of time and storage space.

### Snapshot
A snapshot backup is a hybrid approach. First, a full (typically read-only) copy of the data is made to the backup media. Next, pointers such as hard links are employed to create a reference table linking the backup data with the original data. The next time a backup is made, an incremental backup is made instead of a full backup and the pointer reference table is copied and updated.