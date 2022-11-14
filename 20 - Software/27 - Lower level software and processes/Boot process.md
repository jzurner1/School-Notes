The steps that a computer takes when it turns on.

First, the CPU initializes itself and looks to the BIOS for its first instructions. It runs POST, which makes sure the hardware is functioning properly. Next, it looks for an OS to load, which in turn loads the neccessary device drivers to control devices. Once the drivers are loaded, the user can access the system's applications and begin to work.

# BIOS startup
First, the BIOS runs a bootloader program, a small program that initializes the necessary hardware to find and run the full operating system program. It's often found at another location on the same hard drive but can exist on a separate storage device.

The bootloader usually has a configuration file so you can tell it where to find the actual operating system file to run or, alternatively, produce a small menu allowing the user to boot between multiple operating systems.

To begin, the BIOS needs to know where the bootloader program is located. There are several options for locations, including an internal or external hard drive, a CD or DVD drive, a USB stick, an ISO file, or a network server using NFS, HTTP, or FTP. For hard drives, you need to designate the partition where the bootloader should be loaded. This is done by defining a master boot record (MBR).

A master boot record is the first sector on the first hard drive partition on the system. There is only one MBR for an entire computer system. The BIOS looks for the MBR and reads the program stored there into the memory.

Since the bootloader program must fit in one sector, it must be very small, so it can't do much. The bootloader program mainly points to the location of the actual operating system kernel file stored in a boot sector or a separate partition installed on the system. There are no hard limits on the size of the kernel boot file.

# UEFI startup
Instead of relying on a single boot vector on a hard drive to hold the bootloader program, UEFI specifies a special disk partition called the EFI system partition (ESP) to store bootloader programs. This allows for any size of bootloader program plus the ability to store multiple bootloader programs for multiple operating systems.

The ESP setup utilized the old Microsoft file allocation table (FAT) filesystem to store the bootloader. On Linux, the ESP is usually mounted in the `/boot/efi` folder with the `.efi` filename extension, such as `linux.efi`. Not all Linux distributions support the UEFI framework, however.

The UEFI firmware utilizes a built-in mini bootloader, sometimes called a boot manager, that allows you to configure which bootloader program file to launch. You need to register each individual bootloader file you want to appear at boot time in the boot manager interface menu.

Once the firmware finds and runs the bootloader, it is on to the bootloader to continue the process.