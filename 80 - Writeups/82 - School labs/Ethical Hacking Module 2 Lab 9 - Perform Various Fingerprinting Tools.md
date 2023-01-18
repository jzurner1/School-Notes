# Description
The information gathered in the previous steps may not be sufficient to reveal the potential vulnerabilities of the target. There could be more information available that could help in finding loopholes in the target. As an ethical hacker, you should look for as much information as possible about the target using various tools. This lab activity will demonstrate what other information you can extract from the target using various footprinting tools.

# Process
1. Open the Parrot Security machine
2. Open MATE terminal
3. Type `sudo su` and the password to switch to root
4. `cd` to the root directory
5. Enter `recon-ng` to launch the command line application
6. Type `help` to see the available commands
7. Type `marketplace install all` to install all available modules
8. After installing, type `modules search` to show all the available modules
9. Type `workspaces` to show commands related to workspaces
10. Create a workspace with `workspaces create CEH`
11. Show all workspaces with `workspaces list`
12. Add a domain to perform network recon with `db insert domains`
13. In the domain text section that pops up, type `certifiedhacker.com`, which adds it to the workspace
14. Press enter to skip the notes text section
15. Type `modules load brute` to view all the modules that relate to brute forcing
16. To load one of the modules, do `modules load recon/domains-hosts/brute_hosts`
17. Type `run` and press enter, which will begin to harvest the hosts
18. Type `modules load reverse_resolve`
19. Type `modules load recon/hosts-hosts/reverse_resolve`
20. Type `run` to begin the reverse lookup
21. Type `show hosts` to display harvested hosts from both tools
22. Type `back` to return to the CEH attributes terminal
23. Type `modules load reporting`, then `modules load reporting/html`
24. To set options, do `options set FILENAME /root/Desktop/results.html`
25. Continue with `options set CREATOR joey`
26. Finish with `options set CUSTOMER Certifiedhacker Networks`
27. Type `run` to create a report
28. Type `exit` to close `recon-ng`
29. Open the desktop and open the `results.html` file in Firefox
30. Observe the results
31. Close Firefox and reopen the terminal
32. Type `recon-ng` to open the tool
33. Type `workspaces create reconnaissance` to create a new workspace
34. Type `modules load recon/domains-contact/whois_pocs`
	1. This modules uses the ARIN Whois RWS to harvest POC data for a domain
35. Type `options list` to see the required options
36. Type `options set SOURCE facebook.com` to add Facebook as a target domain
37. Type `run` to begin the scan
38. Return to the workspaces terminal with `back`
39. Type `modules load recon/profiles-profiles/profiler`
40. Type `options set SOURCE MarkZuckerberg`
41. Type `run` to let it run
	1. This module searches for a username and returns the URL of the profile
42. Return to the workspaces terminal with `back`