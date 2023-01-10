# Description
In this lab, you will learn to get information about the TCP (Transmission Control Protocol) ports. TCP establishes connections to recover packets that are lost during transmission. `Get-NetTCPConnection` gets information about the current connection statistics while `Select-Object LocalPort,Remoteport` selects specified properties of the connection statistics..

# Process
1. Open PowerShell
2. Type `Get-NetTCPConnection | Select-Object LocalPort,Remoteport`