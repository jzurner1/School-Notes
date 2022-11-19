There are a number of approaches used to authenticate users.

# Multifactor
[[Multifactor authentication|Multifactor authentication]] (MFA) requires multiple factors to log in. This may mean:
- Something you know, such as a password
- Something you are, such as a fingerprint
- Something you have, such as a smart card
- Something you perform, such as connecting to a specific network

Today, smartphones are often used in MFA.

# TACACS+
Terminal access controller access control system plus (TACACS+) is a Cisco-proprietary TCP-based protocol. It has three separate and distinct sessions/functions for authentication, authorization, and accounting (AAA). It is simple to RADIUS (below) but uses TCP instead of UDP. It uses TCP port 49 by default and takes a client/server model approach.

# RADIUS
Remote authentication dial-in user service (RADIUS) is a UDP-based protocol used to communicate with an AAA server. Unlike TACACS+, it does not encrypt an entire authentication packet, just the password. It does offer other features, and is a standards-based protocol and is not proprietary. It uses UDP port 1812 for authentication and UDP port 1813 for accounting.

# Single sign on
Single sign on (SSO) allows a user to authenticate only once to gain access to multiple systems or applications, without requiring an independent authentication for each system/application.

# LDAP
Lightweight directory access protocol (LDAP) permits a set of standards for the storage and access of user account information. Many proprietary user stores support LDAP for ease of access such as Microsoft's Active Directory. By default it is unsecured over port 389, but it can be secured with LDAP over TLS/SSL (LDAPS) on port 636.

# Kerberos
Kerberos is a client/server authentication protocol that supports mutal authentication between a client and a server. With Kerberos, a trusted third party, or key distribution center (KDC), hands out tickets that are used instead of username and password clients.

![[Pasted image 20220924181020.png]]

# Local authentication
Local authentication refers to a network device authenticating the user with a database of user account information stored on the device itself. It is often an important fallback authentication method when another (external) method fails.

# 802.1X
IEEE 802.1X is a type of network access control that involves permitting or denying a wireless or wired LAN client access to a network.

# EAP
Extensible authentication protocol (EAP) specifies how authentication is performed by 802.1X. There are a variety of EAP types.