Attackers can use the web application hacking methodology to gain knowledge of a particular web application to compromise it successfully. This methodology allows them to plan each step in detail to increase their chances of successfully hacking the application.

## Footprint web infrastructure
[[Footprinting|Footprinting]] is the process of gathering complete information about a system and all its related components, as well as how they work. It involves the following tasks:
- **Server discovery** - Attempting to discover the physical servers that host web applications using techniques such as Whois lookup, DNS interrogation, [[Port scanner|port scanning]], and so on
- **Service discovery** - Discovering the services running on web servers to determine whether they can be used as attack paths for the web application. This can be done with tools such as [[Nmap|Nmap]] to find services running on open ports to exploit them
- **Server identification** - Using banner grabbing or other techniques to identify information about a web server, such as the make and version. This can be done with [[Telnet|Telnet]] or other tools
- **Firewall discovery** - Determining whether or not a server is using a web application firewall (WAF). This can be done with tools like wafw00f.
- **Hidden content discovery** - Finding resources that aren't normally available. This can be done through web spidering/crawling, among other ways

## Analyze web applications
After a web server has been analyzed, an attacker can look at the web application itself. This can involve the following:
- **Identify entry points for user input** - These can later be used as gateways for attacks
- **Identify server-side technologies** - These technologies may be used to generate dynamic web pages requested by clients; they are stored internally on the server. This may include ASP, [[ASP.NET|ASP.NET]], ColdFusion, JSP, PHP, Python, and [[Popular stacks|stacks]] such as Ruby on Rails. Tools include httprint and WhatWeb
- **Identify server-side functionalities** - The ability of a server to execute programs on output web pages. User requests stimulate the scripts residing on the web server to display interactive web pages or websites. The server executes server-side scripts, which are invisible to the user. Tools include GNU Wget, BlackWidow, and Teleport Pro. Some URLs may also reveal database information
- **Identify files and directories** - This may result in the exposure of critical files and directories; can be done with tools like Gobuster
- **Identify web application vulnerabilities** - Some web applications may not follow secure coding practices and may leave flaws that can be exploited
- **Map the attack surface** - Used to target specific vulnerable areas and identify the various attack surfaces uncovered by the applications and their vulnerabilities

![[Pasted image 20230217174224.png]]