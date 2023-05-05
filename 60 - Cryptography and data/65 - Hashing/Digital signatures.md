Digital signatures are one practical implementation of [[Hashing|hashing]]. In essence, a digital signature is a cryptographic token that provides authentication and data verification.

It is simply a message digest (a fixed size, numeric representation of the contents of a file) of the original plain-text data, which is then encrypted and sent along with the ciphertext.

When the receiver decrypts the digital signature with the sender's public key, they can use the message digest to verify the integrity of the file.