Some clients are configured to forward their packets, which are seemingly destined for the internet, to a proxy server instead. The server receives the client's request and sends it to the internet on behalf of the client. When a response is received, it is sent to the proxy server, then the client.

![[Pasted image 20220903123205.png]]

One benefit of this arrangement is security. If all requests go to the internet through the proxy server, the IP addresses of the network devices inside the network are hidden from the internet.

Another benefit is the bandwidth savings because many proxy servers perform content caching. For example, if one client visits a website, the graphics of the home page may be stored on the hard drive and reused for the next time a client accesses the website.

One last use is content filtering and restricting, such as in a company to block social media sites.