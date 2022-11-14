Simple network management protocol is a protocol used to monitor and manage network devices. It uses UDP ports 161 and 162.

SNMP began in 1988 and has since become the de facto standard for network management. Originally, it was intended to manage network nodes such as servers, routers, and switches, but now it works for entire networks.

# Overview
SNMP provides a way for network administrators to query remote network devices and servers to obtain information about their configuration, status, and performance. It operates in a simple client/server paradigm, where network devices and servers run an SNMP server service that listens for requests from SNMP client packages. The SNMP client sends requests for data from the SNMP server.

# Components
SNMPv1 and SNMPv2c specify three major components of an SNMP solution:

### SNMP manager
An SNMP manager, also known as a network management system (NMS), runs a network management application.

### SNMP agent
An SNMP agent is a piece of software that runs on a managed network device such as a router or client.

### MIB
Information about a managed device's resources and activity is defined by a series of objects. The structure of these objects is defined by a managed device's management information base. Interfaces and their details such as errors, utilization, and other performance metrics can be monitored and reported via SNMP.

It is a hierarchical collection of MIB variables that stores the data that SNMP relies on. They are identified using a unique object identifier (OID) for each variable, and the OIDs are organized in a hierarchical tree-like structure. SNMP is efficient at scanning the tree and extracting the OIDs and values of variables that are needed to monitor or reconfigure a network device.

# Message types
Multiple SNMP messages might be sent between an SNMP manager and a managed device, and there are three broad types of message:

### Get
An SNMP get message retrieves information from a managed device

### Set
An SNMP set message sets a variable in a managed device or triggers an action on a managed device

### Trap
An SNMP trap message is an unsolicited message sent from a managed device to an SNMP managers, notifying the SNMP manager about a significant event that occured on the managed device

# Walking
SNMP management software can make requests for each of the MIB objects from an SNMP agent. This is referred to as an SNMP walk because the management software is logically "walking" the entire MIB tree to gather information from the agent.

# Security
SNMP offers security against malicious users attempting to collect information from a managed device, change the configuration of a managed device, or intercept the information being sent to an NMS. However, the integrated security is considered weak. Specifically, it uses community strings to gain read-only access or read/write access to a managed machine. A community string is basically a password. In addition, many SNMP-compliant devices today have the read-only community string set to public by default and the read/write community string set to private. This lets attackers read information without issues.

# SNMPv3
SNMPv3 offers more security than SNMPv1 or SNMPv2c. First, it is important to understand some ideas:

### Security model
A security model devines an approach for user and group authentication. SNMPv1, SNMPv2c, and SNMPv3 are examples of this.

### Security level
Security level defines the type of security algorithm performed on SNMP packets. There are three levels discussed here:

- noAuthNoPriv - The no authorization, no privacy security level uses community strings for authorization and does not use encryption to provide privacy.
- authNoPriv - The authorization, no privacy security level provides an authorization using hashed message authentication code (HMAC) with message digest 5 (MD5) or secure hash algorith (SHA). However, no encryption is used.
- authPrive - The authorization and privacy security level offers HMAC, MD5, or SHA authentication and provides privacy through encryption. Specifically, the encryption uses the cipher block chaining (CBC) data encrytion standard (DES) (DES-56) algorithm.

### Security model and level overview
SNMPv3 is still considered strong enough for today's networks, especially with the additions that have been made to it to make it more secure.

![[Pasted image 20220918112025.png]]

### Security enhancements
Specifically, SNMPv3 offers three primary security enhancements over SNMPv1 and SNMPv2c:

- Integrity - Using hashing algorithms, SNMPv3 ensures that an SNMP message was not modified in transit
- Authentication - Hashing allows SNMPv3 to validate the source of an SNMP message
- Encryption - Useing the CBC-DES (DES-56) encryption algorithm, SNMPv3 provides privacy for SNMP messages, making them unreadable by an attacker who might capture a packet.

### Architectural differences
In addition to its security enhancements, SNMPv3 differs architecturally from SNMPv1 and SNMPv2c. SNMPv3 defines SNMP entities, which are groupings of SNMP components. In the image below, SNMP applications and an SNMP manager combine into an NMS SNMP entity, whereas an SNMP agent and MIB combine into a managed node SNMP entity.

![[Pasted image 20220918112541.png]]
