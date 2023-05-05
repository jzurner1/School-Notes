# Description
To fully understand Computer Forensics, it is essential that you understand how the operating systems and file systems work, and how to utilize computer forensics tools that will help you recover the artifacts relevant to the case.

# Process
### Section 1: Creating the Windows 10 machine
1. Download VMware Workstation and the Windows 10 ISO file
2. In VMware, press "File > New virtual machine"
3. Do a custom install and press "I will install the OS later"
4. Select "Microsoft Windows" as the OS and "Windows 10" as the version
5. Create a 25gb hard drive
6. Press "customize hardware" to see the new window
7. In memory, select an appropriate amount; I chose 4096MB
8. In processors, I chose 8 processor cores
9. For the network adapter, choose "Host-only"
10. Press "Close" and "Finished" to create the machine

### Section 2: Installing Windows
1. Right click the machine and press "Settings", then "CD/DVD (SATA)"
2. Press "Use ISO image file" and browse to the Windows 10 ISO file and press "OK"
3. Click "Play virtual machine"
4. At the Windows setup screen, press "Next" then "Install now"
5. Press "I don't have a product key"
6. Select "Windows 10 Pro" as the version
7. Agree to the software license and press "Custom install"
8. Press next until the installation begins
9. After the intallation, create a user and password
10. Run through the rest of the steps and finalize the installation

### Section 3: Post installation
1. In the VMware workstation, click "Install VMware Tools"
2. In the virtual machine, open "This PC" and double click the VMware Tools drive
3. Run through the installation and click "Yes" to restart the virtual machine
4. After restarting, right click the start menu button and click "Run"
5. Enter `sysdm.cpm` to open the system properties window
6. Change the computer name and other settings as needed
7. Close the window and restart to let the changes take effect

### Section 4: Dumping and examining the registry
1. Download the class-specific software tools ISO file
2. While the Windows virtual machine is running, press "Edit virtual machine settings"
3. Click on the CD/DVD icon and click browse, and choose the new ISO file
4. Make sure that under "Device status", both boxes are checked
5. Press "Okay" and return to the desktop
6. Create a new folder on the desktop
7. Open "This PC" and open the new D: drive
8. Find the program called "FTK imager" (in the imager folder) and run it as administrator
9. Click the gold box to open the "Obtain system files" window
10. Press "Browse" and navigate to the new folder on the desktop
11. Under options, disable "Minimum files" and enable "Password recovery"
12. Close all the other folders and open the desktop folder to see if the files were created
13. Return to the D: drive and open the WRR.exe file
14. In the new window, press "File > Open" and in the desktop folder, open "system"
15. Browse through the data
16. Repeat the process for the "software" file and the "SAM" file