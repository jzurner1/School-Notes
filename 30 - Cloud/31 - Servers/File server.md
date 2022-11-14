A file server is a type of server that allows network clients to access shared files. It is almost essential in any business environment.

In a local network, there are two main methods for sharing files, peer-to-peer and client/server.

In a peer-to-peer network, one workstation allows another workstation to access files stored locally on its hard drive. This method allows collaboration between two clients but can be more difficult for larger numbers of people.

In a client-server network, a centralized file server is used to share files that multiple clients can access and modify as needed. However, an administrator must control who has access to which files and folders to protect them from unauthorized access.

There are two common server software packages used for sharing files, NFS and Samba.

### NFS
The network file system is a protocol used to share folders in a network environment. With NFS, a Linux system can share a portion of its virtual directory on the network to allow access by clients as well as other servers.

In Linux, the software package used to accomplish this is nfs-utils. This package provides both the drivers to support NFS and the underlying client and server software to both share local folders on the network and connect to remote folders shared by other Linux systems on the local network. Using nfs-utils, a Linux system can mount remotely shared NFS folders almost as easily as if they were on a local hard drive partition.

### Samba
The default file sharing method used in Windows is the system message block (SMB) protocol. The Samba software package was created to allow Linux systems to interact with Windows clients and servers with the Linux system acting as either a client or a server. It requires some work in configuration with parameters to manage access.