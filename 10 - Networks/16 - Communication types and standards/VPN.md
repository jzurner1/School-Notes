A virtual private network supports secure remote connections between sites over an untrusted network such as the internet. The two main categories of VPN are site-to-site and client-to-site.

A site-to-site VPN connects two sites as an alternative to a leased line. No software is required for the connection.

![[Pasted image 20220925182059.png]]

A client-to-site VPN connects a remote user with a site as an alternative to dial-up or ISDN connectivity. This form of VPN requires software on the client's computer to connect to a centralized VPN termination device. One very popular option for client-to-site VPNs is a clientless VPN, meaning that there is a client software piece but it is attached to the web browser.

![[Pasted image 20220925182246.png]]

Although a VPN tunnel might physically pass through multiple service provider routers, it will appear to be a single hop from the perspective of the routers at each end of the tunnel.

Another important consideration with VPNs is whether it is a split tunnel or full tunnel configuration. With a full tunnel configuration, all of the end-user's traffic goes through the VPN. With a split-tunnel configuration, you can choose what traffic goes through the VPN. This requires less bandwidth but needs more configuration.

IPSec is a VPN technology that is used to traverse untrusted networks. Internet key exchange (IKE) is a protocol for IPSec. While IPSec provides encryption between authenticated peers using encryption keys that periodically change, IKE allows administrators to manually configure keys.