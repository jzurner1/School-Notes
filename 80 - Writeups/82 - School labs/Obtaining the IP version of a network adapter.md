# Description
In this lab, you will learn to obtain the IP version of a network adapter. IPv4 was the first version of IP, which is used to identify devices on a network. IPv6 is used to fulfill the need for more Internet addresses.

# Process
1. Open PowerShell
2. Enter `(Get-NetIPInterface) | Select-Object InterfaceAlias,AddressFamily` and press enter