The three primary goals of network security: confidentiality, integrity, and availability.

# Confidentiality
Keeping data private by physically or logically restricting access to it or encrypting traffic traversing a network.

A network that provides confidentiality may use network security mechanisms such as firewalls and access control lists (ACLs) to prevent unauthorized access to resources, require appropriate credentials, and encrypt any traffic going through the network that could be intercepted.

One of the key ways that confidentiality can be achieved is with encryption, which allows a packet to be encoded in such a way that it can be decoded by an intended party but not someone that intercepts it. Most encryption algorithms use a key.

# Integrity
Data integrity is making sure that data is not modified, specifically in transit. A data integrity solution might perform origin authentication to verify that traffic is originating from the source that should send the traffic.

Examples of integrity violations include modifying the appearance of a corporate website, intercepting and altering an e-commerce transaction, and modifying financial records that are stored electronically.

Hashing is one approach to providing integrity to data transmissions. Hashing involves taking a string of data such as a password and running it through an algorithm, resulting in a hash or hash digest. If a sender sends data along with the hash digest to a recipient, when the recipient gets the data, they can calculate the hash digest and see if they get the same solution. If they do, the data has not been modified in transit.

# Availability
The availability of data is a measure of that data's accessability measured in percent. For example, if a server is up for 99.999% of the year, it has five nines availability.

Attackers can compromise the availability of a network by sending improperly formatted data to a networked device, resulting in an unhandled exception, or by flooding a network system with an excessive amount of traffic or requests in a DoS attack.