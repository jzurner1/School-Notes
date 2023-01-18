This lab is an introduction to mode recon tools such as Netcraft, Peekyou, theHarvester, Tor, and Censys.io.

# Description
As a professional ethical hacker or pen tester, you should be able to extract a variety of information about your target organization from web services. By doing so, you can extract critical information such as a target organization’s domains, sub-domains, operating systems, geographic locations, employee details, emails, financial information, infrastructure details, hidden web pages and content, etc.

Using this information, you can build a hacking strategy to break into the target organization’s network and can carry out other types of advanced system attacks.

# Process
1. Open Firefox
2. In a new tab, navigate to [Netcraft](https://www.netcraft.com)
3. Select the "resources" dropdown and then "site report"
4. Under "What's that site running", enter `https://www.eccouncil.org`
5. Browse the site for interesting information
6. Under the "Network" section, select the domain to view the subdomains
7. Open a new tab
8. Navigate to [Peekyou](https://www.peekyou.com)
9. In the fields, enter `Satya`, `Nadella`, and `Washington, DC`
10. Browse the freely available information
11. Close the Windows machine and open the provided Parrot Security machine
12. Open MATE Terminal
13. Type `sudo su` and the password to switch to the root account
14. `cd` to the root directory
15. Enter `theHarvester -d microsoft.com -l 200 -b baidu`
	1. `-d` specifies the domain or company
	2. `-l` specifies the number of results
	3. `-b` specifies the data source
16. View the results
17. Switch back to the Windows machine
18. Open the Tor browser
19. Press "Connect" in the window and wait for the connection
20. Before doing anything in Tor, open Firefox and navigate to Google
21. Search something that is clearly illegal, such as `Hacker for hire`
22. Do the same search on Tor and compare the results
23. In this case, Tor should be used for recon and similar tools
24. Close out of Tor and open a new Firefox tab
25. In the search bar, navigate to [Censys.io](https://search.censys.io)
26. In the search field, enter `www.eccouncil.org`
27. Click on any one of the hosts to view it
28. Observe the available information, such as operating system and location