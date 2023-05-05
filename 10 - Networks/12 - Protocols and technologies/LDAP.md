Lightweight directory access protocol is a [[Protocol|Protocol]] that provides directory services to network clients. It uses TCP port 389. The secure version is LDAPS. It was created to provide simple network authentication services to multiple applications and devices on a local network.

### Structure
LDAP manages information in a hierarchical directory structure. Each node in the tree represents an object, such as a user, group, or resource that can be accessed, and each one has a unique identifier called a distinguished name (DN). This DN is similar to a file path, as it is made up of the object's name and the names of all the parent objects up to the root.

### Access
To access information on an LDAP server, a client application sends a request to the LDAP server using the LDAP protocol. The request usually includes a search query that includes the object(s) to be retrieved, along with any other criteria or filters. The LDAP server processes the request and searches the directory for the results, and sends those back in one of many formats.