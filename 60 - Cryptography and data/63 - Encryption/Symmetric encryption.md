Symmetric encryption is a key system where all parties have the same [[key|key]]. It is also known as a secret key system.

The keys are used to both [[Encryption|encrypt]] and [[Decryption|decrypt]] messages, and must be kept secret. This means that the keys must be distributed securely, which presents a challenge for large-scale use. This is solved by the slower but more secure [[Asymmetric encryption|asymmetric encryption]].

![[Pasted image 20220924132126.png]]

### Types
- **DES** - Data encryption standard is an older algorithm that uses a 56-bot key and is now considered deprecated
- **3DES** - Triple DES uses three 56-bot keys for a total of 168 bits and is stronger than DES. It has three keying options: 1) all three keys can be different, 2) two of the three keys may be the same, or 3) all three keys may be the same to maintain backward compatibility with DES
- **AES** - Advanced encryption standard is the preferred symmetric encryption algorithm. It is available with 128-, 192-, and 256-bit keys, where 128 is moderately strong and 256 is considered unbreakable. It is used for many applications such as wireless, mobile, VPNs, and web security applications.