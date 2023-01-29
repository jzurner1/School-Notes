New Technology LAN Manager (NTLM) is a suite of security protocols offered by Microsoft to authenticate user identities and protect the integrity and confidentiality of their activity. It uses a challenge-response mechanism to authenticate users.

## Process
The NTLM authentication process usually follows the following step-by-step process:
1. The user provides their username, password, and domain name
2. The client [[Hashing|hashes]] the password and deletes the plaintext version
3. The client sends the plaintext username to the relevant server
4. The server replies to the client with a "challenge", a 16-byte random number
5. The client responds with the challenge encrypted by the hash of the user's password
6. The server sends the challenge, response, and username to the domain controller (DC)
7. The DC retrieves the user's hashed password from the database and uses it to encrypt the challenge
8. The DC compares the encrypted challenge and the client response; if they match, the user is authenticated and access is granted