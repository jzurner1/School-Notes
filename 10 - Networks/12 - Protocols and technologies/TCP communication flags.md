The [[TCP|TCP]] header contains various flags that control the transmission of data across a TCP connection.

There are six flags in total. Four of them (SYN, ACK, FIN, RST) govern the establishment, maintenance, and termination of a connection. The other two (PSH, URG) provide instructions to the system.

Each flag is one bit, either 1 or 0.

## Flag meanings
- The **SYN** flag (synchronize) is used to notify the transmission of a new sequence number. It generally represents the establishment of a three-way handshake between two hosts.
- The **ACK** flag (acknowledgement) confirms the receipt of a transmission and identifies the next expected sequence number.
- The **PSH** flag (push) indicates that the sender has raised the push operation to the receiver, implying that the remote system should inform the receiving application about the buffered data coming from the sender.
- The **URG** flag (urgent) instructs the system to process the data contained in packets as soon as possible; it is processed first.
- The **FIN** flag (finish) indicates that no more transmissions will be sent to the remote system and the connection (established by the SYN flag) is terminated.
- The **RST** flag (reset) is set when there is an error in the current connection; the connection is aborted in response.