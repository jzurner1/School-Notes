# Description
As a professional ethical hacker, you need to gather the DNS information of a target domain obtained during the previous steps. You need to perform DNS footprinting to gather information about DNS servers, DNS records, and types of servers used by the target organization. DNS zone data include DNS domain names, computer names, IP addresses, domain mail servers, service records, and much more about a target network.

Using this information, you can determine key hosts connected in the network and perform social engineering attacks to gather even more information.

# Process
1. Open a command prompt window
2. Type `nslookup` and press enter
3. In the window, type `set type=a`
	1. This configures nslookup to query for the IP address of a domain
4. Type `www.certifiedhacker.com` to search that domain
5. The results will show the DNS server and IP as well as those of the page
6. Type `set type=cname`
	1. This lookup is done against the domain's authoritative name server
7. Type `certifiedhacker.com`
8. This will show more information such as the authoritative name server
9. Close the command prompt and open Firefox
10. Navigate to [YouGetSignal](https://www.yougetsignal.com)
11. Select "Reverse IP Domain Check"
12. In the field, type `www.certifiedhacker.com` and click "check"
13. View the 15 domains that are also hosted on the same web server
14. Switch over to Parrot Security and open the MATE terminal
15. Type `dnsrecon -r 162.241.216.0-162.241.216.255`
	1. This IP address range includes the previously checked `certifiedhacker` domain