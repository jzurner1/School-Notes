The configuration of adapters and other [[Hardware|Hardware]] is easy if documentation is followed and you know how to obtain device drivers.


# Startup
During startup, BIOS/UEFI plays an important role as part of the startup routine. It checks hardware for errors as part of POST and detects installed adapters and devices. Along with the OS, it also determines what resources to assign to a device or adapter. This information is stored in a part of the CMOS known as the extended system configuration data (ESCD) area. After information is configured there, it stays and does not need to be recomputed until another device is added.

After resources are allocated, the BIOS looks in the saved settings of CMOS to determine which device it should look to first for an operating system. This part of the routine is known as the bootstrap loader. If an operating system in the first specified location is not found, it tries the second device and continues on until one is found.


# Installing drivers
When installing hardware or an adapter in Windows, a driver is required. The OS detects the adapter or hardware installtion and adds the device's configuration information to the registry, which is a central database in Windows that holds hardware information and other data.

For many common devices such as keyboard or mice, Windows includes the driver. When the device is attached, the driver loads, and the device configuration is added to the registry. Another way to get drivers is through Windows updates, which will often include updated drivers.

Some drivers are installed manually as part of the installation process of an adapter. This can be done with the Device Manager in Windows.