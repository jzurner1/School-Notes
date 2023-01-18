This lab is an introduction to recon and tools such as ping, CentralOps, Web Data Exfiltrator, HTTrack Website Copier, and cewl.

# Description
As a professional ethical hacker, you should be able to extract a variety of information about the target organization from its website; by performing website footprinting, you can extract important information related to the target organization’s website such as the software used and the version, operating system details, filenames, paths, database field names, contact details, CMS details, the technology used to build the website, scripting platform, etc. Using this information, you can further plan to launch advanced attacks on the target organization.

# Process
1. Open the Windows 10 machine
2. Open the command prompt
3. Type `ping www.certifiedhacker.com` and press enter
4. Observer the IP address that is revealed
5. Type `ping www.certifiedhacker.com -f -l 1500` and press enter
6. Observe the response as saying "Packets need to be fragmented but DF set"
	1. This means that the packets sent were too large
7. Repeat with `-l 1300`
8. This will succeed, showing that the maximum frame size will be between 1300  and 1500
9. Repeat until you find the maximum frame size, which turns out to be 1472
10. Next, type `ping www.certifiedhacker.com -i 3`
	1. The `-i` flag sets the time to live (TTL)
11. This will expire in transit, showing that you need a higher TTL
12. Open a new command prompt and enter `ping www.certifiedhacker.com -i 2 -n 1`
	1. The `-n` flag specifies the number of ICMP packets, default 4
13. This will expire in transit
14. Try again with `-i 3` and observe the same results
15. Repeat until it stops expiring; this shows the hop count to the target, in my case 18
16. Close the command prompts and open Firefox
17. Navigate to [CentralOps](https://centralops.net)
18. In the "Enter a domain or IP address field", enter `www.certifiedhacker.com`
19. Observe the result, which contains a lot of information about the address
20. Close Firefox and open Web Data Extractor
21. Click "New" to start a new session
22. Enter `http://www.certifiedhacker.com` as the URL and select all the checkboxes
23. Press "OK" then "Start"
24. When it finishes, click the "Meta tags" tab to view the URL, title, keywords, and so on
25. Select the "Emails" tab to view emails extracted
26. Select the "Phones" tab to view information about phone numbers
27. Select the other tabs for other assorted information
28. Save the session
29. Close Web Data Extractor and open HTTrack Website Copier
30. Create a new project
31. When asked to add URLs, add `www.certifiedhacker.com`
32. Click "Set options" and click the "Scan rules" tab
33. Select all the available file types, then press "OK"
34. Click "Disconnect when finished", then "Finish"
35. Click "Browse mirrored website" and examine the website
36. Close the Windows machine and open the Parrot Security machine
37. Open MATE terminal
38. Type `sudo su` and the password to switch to the root account
39. `cd` into the root directory
40. Type `cewl -d 2 -m 5 www.certifiedhacker.com` and press Enter
	1. `-d` specifies the spidering depth
	2. `-m` specifies the minimum word length
41. Browse the resulting wordlist