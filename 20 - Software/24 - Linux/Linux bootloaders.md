The bootloader program is part of the boot process, and Linux bootloaders were designed specifically for the Linux boot process. Bootloaders help bridge the gap between the system firmware and the full Linux operating system kernel.

The most common versions of the Linux bootloader are Linux Loader (LILO), Grand Unified Bootloader (GRUB) legacy, and GRUB2.

### LILO
Originally, only the LILO bootloader was available and it was extremely limited. The configuration was stored in a single file, `/etc/lilo.conf`, which defines the systems to boot. Unfortunately, LILO doesn't work with UEFI, so it is quickly being replaced.

### GRUB Legacy
The original version of GRUB was created in 1999 to provide a more robust and configurable bootloader to replace LILO. It quickly became the default bootloader for all Linux distributions with both BIOS and UEFI.

### GRUB2
GRUB2 was created in 2005 as a total rewrite of the GRUB Legacy system. It supports advanced features such as the ability to load hardware driver modules and using logic statements to dynamically alter the boot menu options depending on the conditions, such as if an external hard drive is detected.

# GRUB Legacy Basics
GRUB Legacy allows you to select multiple kernels and/or operating systems using a menu interface and an interactive shell. You can configure the menu interface to provide options for each kernel or operating system you want to boot with.

When using the GRUB Legacy interactive menu, you need to tell it what options to show using special GRUB menu commands.

The GRUB Legacy system stores the menu commands in a file called `menu.lst` in the `/boot/grub` folder. Red Hat and related versions (such as CoinOS) use `grub.conf` instead of `menu.lst`.

The GRUB Legacy configuration file consists of two sections, global definitions and operating system boot definitions.

The global definitions section defines commands that control the overall operation of the GRUB Legacy boot menu. These global definitions must appear first in the configuration file. The table below shows the only settings that you can make:

![[Pasted image 20221024185931.png]]

