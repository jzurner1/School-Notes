# Description
Attackers use digital Trojan horses to trick the victim into performing a predefined action on a computer. Trojans are activated upon users’ specific predefined actions, like unintentionally installing a piece of malicious software or clicking on a malicious link, and upon activation, it can grant attackers unrestricted access to all data stored on compromised information systems and cause potentially immense damage. For example, users could download a file that appears to be a movie, but, when opened, it unleashes a dangerous program that erases the hard drive or sends credit card numbers and passwords to the attacker.

Trojan horses work on the same level of privileges as victims. For example, if a victim has the privileges to delete files, transmit information, modify existing files, and install other programs (such as programs that provide unauthorized network access and execute privilege elevation attacks), once the Trojan infects that system, it will possess the same privileges. Furthermore, it can attempt to exploit vulnerabilities to increase its level of access, even beyond the user running it. If successful, the Trojan could use the increased privileges to install other malicious code on the victim’s machine.

An expert security auditor or ethical hacker needs to ensure that the organization’s network is secure from Trojan attacks by finding machines vulnerable to these attacks and making sure that anti-virus tools are properly configured to detect such attacks.

The lab tasks in this exercise demonstrate how easily hackers can gain access to the target systems in the organization and create a covert communication channel for transferring sensitive data between the victim computer and the attacker.

# Process
### Task 1 - Gain Control over a Victim Machine using the njRAT RAT trojan

Attackers use Remote Access Trojans (RATs) to infect the target machine to gain administrative access. RATs help an attacker to remotely access the complete GUI and control the victim’s computer without his/her awareness. They can perform screening and camera capture, code execution, keylogging, file access, password sniffing, registry management, and other tasks. The virus infects victims via phishing attacks and drive-by downloads and propagates through infected USB keys or networked drives. It can download and execute additional malware, execute shell commands, read and write registry keys, capture screenshots, log keystrokes, and spy on webcams.

njRAT is a RAT with powerful data-stealing capabilities. In addition to logging keystrokes, it is capable of accessing a victim’s camera, stealing credentials stored in browsers, uploading and downloading files, performing process and file manipulations, and viewing the victim’s desktop.

This RAT can be used to control Botnets (networks of computers), allowing the attacker to update, uninstall, disconnect, restart, and close the RAT, and rename its campaign ID. The attacker can further create and configure the malware to spread through USB drives with the help of the Command and Control server software.

1. Log in to the Windows 10 machine
2. Open njRat v0.7d.exe
3. Press start on the default port, in this case 5552
4. Click the Builder button on the bottom left
5. In the pop-up, make sure that `Registy StarUp` is selected and hit build
6. Save the file
7. Transfer the file to the Windows Server 2016 machine's desktop with any method
8. Switch to the machine and run the executable
9. Switch back to the Windows 10 machine and observe the newly created connection
10. Right-click on the victim name and click manager
11. Double-click any directory in the left pane and observe the files
12. Click on the process manager and observe the processes
13. Click on connections and observe the connections
14. Click on registry and observe the registry files
15. Click on the remote shell button, which will launch a remote command prompt
16. Type `ipconfig/all` to view all the interfaces on the victim's machine
17. Close the manager window and right-click on the victim name
18. Click run file
19. Right click on the victim name and click remote desktop
20. This will launch a remote desktop connection without the victim's awareness
21. Hover the mouse cursor over the top center area of the window
22. In the dropdown menu, select mouse
23. Play around with the RDP connection for a while, then close out of the RDP window

### Task 2 - Hide a Trojan using SwayzCryptor and Make it Undetectable to Various Anti-Virus Programs

At present, numerous anti-virus software programs have been configured to detect malware such as Trojans, viruses, and worms. Although security specialists keep updating the virus definitions, hackers continually try to evade or bypass them. One method that attackers use to bypass AVs is to “crypt” (an abbreviation of “encrypt”) the malicious files using fully undetectable crypters (FUDs). Crypting these files allows them to achieve their objectives, and thereby take complete control over the victim’s machine.

Crypter is a software that encrypts the original binary code of the .exe file to hide viruses, spyware, keyloggers, and RATs, among others, in any kind of file to make them undetectable by anti-viruses. SwayzCryptor is an encrypter (or “crypter”) that allows users to encrypt their program’s source code.

1. Open the Windows 10 machine and a browser
2. Navigate to the VirusTotal website
3. Select "choose file" and navigate to the exe file created in task 1, then open it
4. Click "confirm upload"
5. Observe the results that say that 62 of 71 antivirus programs have scanned it as malicious
6. Open SwayzCryptor.exe
7. In the SwayzCryptor GUI, click the ellipses below file
8. Navigate to and select the exe file from task 1
9. Once the file is selected, check the options "start up", "mutex", and "disable UAC" and click encrypt
10. Save the file where you want to, and hit close when the encryption is finished
11. Reopen VirusTotal and upload the newly saved file
12. Observe that this time, only 40 of 71 antivirus programs scanned it as malicious