A web server is a server built to host a website. Most web servers are run on Linux, specifically a Linux server.

# Programs
There are a number of programs that can be used to build a Linux web server.

### Apache
The Apache web server is the most popular web server on the internet due to its modularity. Each advanced feature is build as a plug-in module. The server administrator can pick and choose which modules a particular server needs for a particular application, thereby reducing the amoung of memory required to run the Apache server daemons on the system.

### nginX
Designed as a replacement for the Apache web server, nginX improves on performance and provides some additional features such as working as a web proxy, mail proxy, web page cache, and even load-balancing server.

The core nginX program has a smaller memory footprint so it can handle over 10,000 simultaneous network client connections.

This type of web server is growing in popularity, especially in high-traffic web environments. One configuration that's becoming popular is to use a combination og nginX web server as a load-balancing front end to multiple Apache web servers on the backend, taking advantage of nginX's strong traffic handling and Apache's versatility in handling web applications.

### lighthttpd
For lightweight web servers, lighthttpd can be used. It is known for low memory usage and low CPU usage, making it ideal for smaller server applications such as in embedded systems. It also incorporates a built-in database, allowing you to combine basic web and database services in a single package.