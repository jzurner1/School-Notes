High-level data link control (HDLC) is a [[Bit-oriented protocol|bit-oriented]] [[Data-link protocols|data-link protocol]].

- Very widely used
- The basis for many other data link protocols
- Point-to-point topology, so it doesn't need a destination field as there is only one possible destination for the data
- Creates a WAN link between two routers so they can forward packets to the routers' other attached LANs

# Format

![[Pasted image 20230112110334.png]]

- The **beginning sequence** and **ending sequence**, also called flags, are `0111 1110`
- These will be attached to any and every frame
- Also transmitted during any idle times to keep the nodes synchronized

- The **header** contains the **address** and **control** field in 8 bits each
- The control field is somewhat outdated and rarely used

ISO standard HDLC doesn't contain a type field, but some routers need to know the type of packet within the frame. Cisco has a proprietary version of HDLC that adds a 2-byte type field between the header and body.

- The **body** or payload has a variable size
- Whatever is received from the network layer is placed in the body

- The **cyclic redundancy check (CRC)** is used for error detection


# Types
There are three general types of HDLC frames, each identified by the control field in the header.

- A frame is an **I-frame** if the first bit of the control field is 0
- I-frames, short for information frames, hold information

- A frame is an **S-frame** if the first two bits of the control field are 10
- S-frames, short for supervisory frames, are used for error control and flow control

- A frame is a **U-frame** if the first two bits of the control field are 11
- U-frames, short for unnumbered frames, are used for miscellaneous things