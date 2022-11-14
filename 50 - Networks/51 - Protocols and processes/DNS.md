Domain name system is a protocol that resolves domain names to their corresponding IP address using both TCP and UDP. Uses port 53 in both cases.

DNS performs the task of resolving a domain name such as www.google.com to a corresponding IP address (in this case 8.8.8.8). Because routers make their forwarding decisions based on layer 3 information, an IP packet needs to contain IP address information, not DNS names. However, humans are better at remembering names than large numbers.

All devices are recognized by an IP address. Local devices can be recognized with a hostname.

# Older system
Back in the old days, a text file stored locally on each computer mapped host names to IP addresses. This let people refer to other computers by name and their computer would translate that name into the corresponding IP address.

Eventually this became impractical as network sizes increased. To overcome the limitations, domain name structure was developed.

# The servers
### Local cache


### Recursive DNS server
The recursive server is usually provided by your ISP, but you can also choose your own. This server also has a local cache of recently looked up domain names. If a result is found locally, this is sent back to your computer. If not, it sends a request to the internet's root DNS servers.

### Root DNS server


### Top-level domain server
The TLD server holds records for where to find the authoritative server to answer the DNS request.

### Authoritative DNS server
The authoritative server, also known as the nameserver, is the server responsible for storing the DNS records for a particular domain name and where any updates to your domain name DNS records would be made.


# The process
1. You enter a URL into a search bar.
2. Your computer checks its local cache to see if the URL is stored there. If not, it sends a request to your recursive DNS server.
3. The recursive server checks its local cache. If nothing is found, it sends a request to the internet's root DNS servers.
4. The root server will redirect you to the top level domain server that corresponds with the URL you entered. For example, if you enter the URL `tryhackme.com`, you will be redirected to the TLD server that deals with .com addresses.
5. The TLD server will redirect the request to the appropriate authoritative server.
6. The authoritative server will find the DNS record and send it back to the recursive DNS server.
7. The recursive DNS server will save a copy and send the DNS record on to you.