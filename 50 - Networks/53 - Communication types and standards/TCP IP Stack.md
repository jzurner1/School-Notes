The OSI model was developed to be generic to most protocols and technologies on the internet, but most traffic on the internet is actually based on the TCP/IP protocol suite. This model is more relevant for most users and was developed by the Department of Defence. It is also known as the **TCP/IP stack** or the **DoD model**.

Unlike the OSI model, there are only four defined layers. These layers are as follows:

- Network interface: this layer corresponds to the OSI model's data link layer and physical layer. It encompasses the technologies offered by those two layers.
- Internet: this layer corresponds to the network layer of the OSI model. Unlike the network layer, which contains multiple routed protocols, the internet layer only contains the IP routed protocol.
- Transport: this layer, obviously, corresponds to the OSI model's transport layer. It contains both TCP and UDP protocols.
- Application: this layer contains all of the OSI model's upper layers (session layer, presentation layer, application layer).


# Application protocols
All application protocols within the TCP/IP stack are identifiable by port numbers. When traffic is sent to another network node, the destination port that it will use, for example 80 for a web server. Your computer will choose a source port greater than 1023, in this example 1248.

![[Pasted image 20220823095918.png]]