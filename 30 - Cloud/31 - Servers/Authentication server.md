An authentication server usually involves sharing user account databases across multiple Linux servers on a network. There are a few methods to achieve this.

### NIS
The network information system (NIS) is a directory service that allows both clients and servers to share a common naming directory. This directory, called the NIS naming directory, is often used as a common repository for user accounts, hostnames, and even email information on local networks. The NIS+ protocol expands on NIS with security features.

The nis-utils package is used for NIS and NIS+ in a Linux environment. It is included in most Linux distribution repositories.

### Kerberos
Kerberos is a secure authentication protocol that uses symmetric-key cryptography to securely authenticate users with a centralized server database. The entire process is encrypted, making it a secure method of logging into a Linux server. It can also be used as a plug-in module for many server applications to authenticate application users.

### LDAP
Lightweight directory access protocol (LDAP) was created to provide simple network authentication services to multiple applications and devices on a local network. The most popular Linux version is OpenLDAP.

OpenLDAP allows you to design a hierarchical database to store objects in a network, specifically in a treelike fashion. This allows you to group objects by types such as users and servers, or by location, or both. This is a very flexible way to design authentication for a local network.