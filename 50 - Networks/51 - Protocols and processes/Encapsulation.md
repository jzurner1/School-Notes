Encapsulation is the process of adding information to data as it travels down the OSI model and TCP/IP (from theapplication layer to the physical layer). The process for the OSI model and TCP/IP are the same besides the names of the layers.

First, as the data enters the transport layer, a segment header is added in front of the data. It is now called a segment. Next, the data goes to the network layer, where a packet header is added in front of the segment. It is now called a packet. Next, the data goes to the data link layer where a frame header is added in front of the packet and a frame trailer is added afterward. It is now called a frame. Lastly, the data is converted into bits and sent through a physical medium.

![[what-is-data-encapsulation-in-networking-process-148532037a490a19.jpg]]

![[osi-model-data-encapsulation-decapsulation2.png]]