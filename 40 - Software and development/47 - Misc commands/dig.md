Domain information groper (`dig`) is a command used for DNS queries and more functionality than the nslookup command.

The syntax of the dig command is `dig @<server> <domain name> <type>`, very similar to nslookup.

| Query type | Result             |
| ---------- | ------------------ |
| A          | IPv4 addresses     |
| AAAA       | IPv6 addresses     |
| CNAME      | Canonical name     |
| MX         | Mail servers       |
| SOA        | Start of authority |
| TXT        | TXT records        |

Domain name is just the website's domain name or URL

Server lets you choose the DNS server that you want to query. There [are tons of servers](https://public-dns.info/) to choose from, but the most common are the ones offered by Cloudflare (1.1.1.1 and 1.0.0.1), Google (8.8.8.8 and 8.8.4.4), and Quad9 (9.9.9.9 and 149.112.112.112).

# Example
To find the TXT records of the tryhackme website, you would enter the following:
`dig tryhackme.com TXT`