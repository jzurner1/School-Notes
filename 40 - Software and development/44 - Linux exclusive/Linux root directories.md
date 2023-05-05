The root directory contains the following directories:

# /bin
The bin folder contains the most basic binaries, which are programs and applications. Commands like ls and cat are stored here.

# /boot
Contains everything that the OS needs in order to boot such as the bootloaders.

# /cdrom
Legacy mounting point for the CDROM

# /dev
Where the devices live. In Linux, everything is a file, and this is where you will find the hardware files. It is usually used by applications and drivers and rarely by users.

# /etc
Where all system-wide configurations are stored, such as for apt. Does not contain configurations for per-user settings.

# /home
Contains individual user folders with personal files and documents. Each user can only access their own folder unless they use admin permissions. Sometimes the /home folder is stored on a different drive or partition, which allows you to reinstall your system and preserve your files.

# /lib, /lib32, /lib64
Where the libraries are stored. Libraries are files that applications can use to perform various functions. They are required by the binaries in /bin and /sbin.

# /media, /mnt
Where to find other mounted drives such as USB sticks, floppy disks, external drives, and second hard drives. Basically all drives except for the main one.

# /opt
"Optional" folder, where manually installed software from vendors reside.

# /proc
Psuedo-files that contain information about system processes and resources. Every process will have a directory here that contains information about that process. This is basically the OS kernel translating information to appear as files.

# /root
The root user's home folder. Doesn't contain the normal user files that regular user accounts use. Requires root permissions to access.

# /run
Used slightly differently in different distributions. Tempfs file system, meaning it runs in RAM and everything disappears when the system shuts down. Used for processes that start early in the boot procedure to store runtime information that they use to function.

# /sbin
System binaries, similar to the bin folder but contains commands that regular users don't have access to.

# /snap
Where snap packages are stored, mainly used by Ubuntu.

# /srv
Service directory where service data is stored. It is usually empty unless you are running a server, in which case you would store the files that would be accessed by external users. Allows for better security because it is located at the root of the drive and allows it to be easily mounted.

# /sys
System folder, a way to interact with the kernel. For example, it may be used to change graphics card settings. Similar to the run directory and is not physically written to the disk.

# /tmp
Temporary files to be used during a session. Usually empties on reboot, but some files stay.

# /usr
User application space where applications are installed that are used by the user as opposed to the system and system administrator. Files stored here are considered nonessential for basic system operation.

# /var
Contains files and directories that are expected to grow in size such as log files and crash reports.