Settings that are changed in [[BIOS|BIOS/UEFI]] are recorded and stored in a complementary metal-oxide semiconductor (CMOS) found in the motherboard chipset. CMOS is memory that requires a small amount of power provided by a small coin-sized lithium battery.

Part of the BIOS/UEFI software routine checks CMOS for information about what components are supposed to be installed, which are then checked as part of the POST routine. POST knows what hardware is supposed to be in the computer by obtaining the settings from CMOS. If the settings don't match, an error occurs.

If the battery inside the CMOS (also known as the CMOS battery) dies, all configuration information is lost and must be re-entered after the battery is replaced.

# Clearing CMOS
Sometimes BIOS/UEFI settings get messed up and the best option is to reset it to factory defaults. This can be done by clearing the CMOS through a menu option, a motherboard switch or push botton, or a back panel push button. This is not the same as flashing the BIOS.

Note: Do not clear the CMOS immediately after upgrading the BIOS/UEFI; power down the system and power it back on first.