Domain name system is a protocol that resolves domain names to their corresponding IP address using both TCP and UDP. Uses port 53 in both cases.

DNS performs the task of resolving a domain name such as www.google.com to a corresponding IP address (in this case 8.8.8.8). Because routers make their forwarding decisions based on layer 3 information, an IP packet needs to contain IP address information, not DNS names. However, humans are better at remembering names than large numbers.

All devices are recognized by an IP address. Local devices can be recognized with a hostname.

### Record types
- **A Record** - Resolve to IPv4 addresses
- **AAAA record** - Resolve to IPv6 addresses
- **CNAME record** - Resolve to another domain name
- **MX record** - Resolve to the address of the servers that handle the email for the domain that is being queried