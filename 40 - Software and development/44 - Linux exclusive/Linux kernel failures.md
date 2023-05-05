A kernel failure is when the Linux kernel stops running in memory, causing the Linux system to crash. This is also known as kernel panic. This is often a result of a software change such as installing a new kernel without a dependency.

### Selecting previous kernels
On boot, many Linux distributions will give you the option to select a previous kernel. This is helpful if a new kernel fails to boot.

![[Pasted image 20221027120215.png]]

### Single-user mode
Sometimes you may need to perform system maintenance such as adding a new hardware module or library file in order to get the system to boot properly. In this case you will want the system to boot up without allowing multiple users to connect, especially in a server environment. This is called single-user mode.

The GRUB menu allows you to start the system in single-user mode by adding the `single` command to the `linux` line in the boot menu. To get there, press the `E` key on the boot option in the GRUB boot menu. Below is a before and after. After entering this, press `Ctrl+X` to boot.
![[Pasted image 20221027122225.png]]
![[Pasted image 20221027122305.png]]

When you do this, the system will boot intro `runlevel 1`, which creates a single login for the root user account. Once you log in as the root user account, you can modify the appropriate modules, init scripts, or GRUB boot menu options necessary to get the system to start correctly.

### Passing kernel parameters
You can add other parameters to the `linux` command line in the GRUB boot menu. This may let you alter the hardware modules that activate or the hardware settings it looks for with specific devices, specifically sound and network cards.