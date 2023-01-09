# Description
In this lab, you will learn to obtain the IP version of a network adapter. IPv4 was the first version of IP, which is used to identify devices on a network. IPv6 is used to fulfill the need for more Internet addresses. `Get-NetIPInterface` gets an IP interface that includes IPv4 and IPv6 addresses and the associated address configuration for the IP interfaces. `Select-Object` selects specified properties of the IP interfaces.

# Process
1. Open PowerShell
2. Type `(Get-NetIPInterface) | Select-Object InterfaceAlias,AddressFamily` and press enter