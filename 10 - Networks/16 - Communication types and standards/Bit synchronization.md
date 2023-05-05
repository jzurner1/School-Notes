For two networked devices to communicate at the physical layer they must agree on when one bit stops and another starts. There are two basic approaches to bit synchronizations:

#### Asynchronous
A sender states that it is about to start transmitting by sending a start bit to the receiver. When the receiver sees this, it starts its own internal clock to measure the next bits. After the sender transmits its data, it sends a stop bit to say that it has finished its transmission.

#### Synchronous
The sender and the receiver synchronize using an external clock that can be referenced by both, such as one provided by the service provider.