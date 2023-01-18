This lab is an introduction to recon and tools such as theHarvester, sherlock, Followerwonk

# Description
As a professional ethical hacker, during information gathering, you need to gather personal information about employees working in critical positions in the target organization; for example, the Chief Information Security Officer, Security Architect, or Network Administrator. By footprinting through social networking sites, you can extract personal information such as name, position, organization name, current location, and educational qualifications. Further, you can find professional information such as company or business, current location, phone number, email ID, photos, videos, etc. The information gathered can be useful to perform social engineering and other types of advanced attacks.

# Process
1. Open the Parrot Security machine
2. Open MATE terminal
3. Enter `sudo su` and the password to switch to root
4. `cd` to the root directory
5. Enter `theHarvester -d eccouncil -l 200 -b linkedin`
6. Observe the results and view the employee information
7. Enter `clear` to reset the terminal screen
8. Navigate to the folder containing the `sherlock` tool
9. Enter `python3 sherlock.py satya nadella`
10. Browse the results and view the provided information
11. Switch to the Windows machine
12. Open Firefox and navigate to [Followerwonk](https://followerwonk.com/analyze)
13. In the screen name search bar, enter `@satyanadella`
14. View the detailed analysis