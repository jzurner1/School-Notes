A port is a number assigned to uniquely identify a connection endpoint and to direct data to a specific service. The ports for TCP and UDP can have different services.

When a computer runs a network service such as a web server, it has to open a port to receive the connection. Ports are necessary for making multiple network requests or having multiple services available as it allows messages to specify which service they are coming from or going to.

When hosting a service, port numbers are preset. For example, a web server will probably use port 443 because it is running the HTTPS protocol. When you send a request to this web server, the destination port will be 443. That is known as an open port because it is open and listening for connections from clients like you.

When sending requests, your computer will select a random unused and unaffiliated port number to use. For example, when sending a request to a web server, your computer may choose to use port 62534. From then on, any messages on this connection will be between your port 62534 and the server's port 443.

Scanning ports is important for most cybersecurity recon. The most popular port scanning tool is nmap.

# Port numbers
[Wikipedia has a full list of ports](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers) that covers both TCP and UDP and shows what services they are used by.