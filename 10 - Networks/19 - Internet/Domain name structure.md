The domain name structure is the structure used to store IP addresses and their corresponding devices in order to make communication between devices more efficient.

# Hosts file
Before DNS, the old system involved a text file (called a hosts file) with system names corresponding to their respective IP address. This text file existed on all computers and had to be updated on all of them when the network changed. This was fine for smaller networks but quickly became impractical as networks grew.

# Example
Suppose there are a few connected networks called network1, network2, and so on. All of these networks have a mail server. If the networks use a hosts file, their mail servers would have to have different names:

```
Mailserver1   192.168.1.1
Mailserver2   192.168.2.1
```

This is fine for just a few networks, but it gets difficult for larger networks. Instead, we use the network names as part of the naming structure. These networks are called domains:

```
Mailserver in Domain1   192.168.1.1
Mailserver in Domain2   192.168.2.1
```

This works but it also gives problems as the number of domains increases. The solution is to arrange them into a hierarchy. This is how URLs are arranged:

![[Pasted image 20221015122041.png]]

This works in a similar way to file trees on computers, where C:\ is the top layer followed by folders such as Temp and Users, which in turn has files for each user.