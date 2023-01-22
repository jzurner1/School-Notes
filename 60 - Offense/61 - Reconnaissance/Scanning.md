Scanning is the process of gathering detailed information about a target using highly complex and aggressive reconnaissance techniques. The purpose is to discover exploitable communications channels, probe as many listeners as possible, and track the ones that are responsive or useful.

## Types of scanning
- **Port scanning** is the process of checking the services running on a target device by sending a sequence of messages in an attempt to determine what services are running and which ones are in a listening state. This can provide information about the operating system and the application currently in use.
- **Network scanning** is a procedure for identifying active hosts on a network, either to attack them or assess the network's security. It will often result in a list of active hosts and IP addresses.
- **Vulnerability scanning** is a method for checking whether a system is exploitable by identifying its vulnerabilities. Vulnerability scanner tools will consist of a scanning engine and a catalog, where the scanning engine browses services and versions and the catalog compares those to known vulnerabilities.

## Firewall evasion
Intrusion detection systems (IDS) and [[Firewall|firewalls]] are security mechanisms intended to prevent an attacker from accessing a network. There are some common techniques to bypass these restrictions, but they may not succeed:
- **Packet fragmentation** is the practice of sending fragmented probe packets to the target, which are reassembled after all of them are received
- **Source routing** is where the attacker specifies the routing path for malformed packets to reach the target
- **Source port manipulation** is the practice of manipulating the source port and replacing it with a common source port
- **IP address decoying** is where the attacker either generates or manually specifies IP addresses of decoys so that the IDS/firewall can't determine the actual firewall
- **IP address spoofing** is where the attacker changes the source IP addresses so that the attack appears to be coming from someone else
- **Creating custom packets**, which can be used to scan the target beyond firewalls
- **Randomizing host order**
- **Sending bad checksums**
- **Proxy servers** to hide the origin of a scan
- **Anonymizers**, which allow packets to bypass internet censors and certain IDS/firewall rules
