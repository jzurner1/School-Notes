New Technology LAN manager is a default authentication scheme that performs authentication using a challenge/response strategy (as detailed below).

NTLM consists of two protocols, NTLM authentication protocol and LAN manager (LM) authentication protocol. Each of these protocols uses a different hash methodology to store user's passwords.

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