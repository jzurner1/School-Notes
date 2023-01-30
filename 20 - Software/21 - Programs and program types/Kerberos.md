Kerberos is a network authentication protocol that provides authentication for [[Client-server|client/server]] applications through secret-key cryptography. It provides mutual authentication in that both the server and the user verify each other's identity. Messages sent through Kerberos are protected against [[Replay attack|replay attacks]] and [[Eavesdropping|eavesdropping]].

Kerberos employs the Key Distribution Center (KDC), which is a trusted third party. It consists of two logically distinct parts: an [[Authentication server|authentication server]] (AS) and a ticket-granting service (TGS). Kerberos uses tickets to prove a user's identity.

Kerberos is the default authentication protocol used by Microsoft, and it replaces [[NTLM|NTLM]].