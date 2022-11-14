When using an SSH client isn't enough, you may need to use some sort of remote desktop software.

Remote desktop software uses a client/server model. The server runs on the remote system while the client runs on the local system.


# VNC
Virtual network computing (VNC) is multiplatform and employs the remote frame buffer (RFB) protocol. This allows a user on the client side to send GUI commands such as  mouse clicks to the server. The server sends desktop frames back to the client's monitor.

It runs on TCP port 5900 + n, where n is the display number. If accessed through a web browser, it is port 5800 + n.

# Xrdp
Xrdp uses the remote desktop protocol (RDP). It provides only the server side of an RDP connection and uses Xvnc to manage the GUI session.

# NX
Compresses the X11 data so that there is less data to send over the network, which improves response time.

# SPICE
Provides connections with KVM virtual machines. Platform independent.