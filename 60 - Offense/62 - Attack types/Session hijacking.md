A type of attack where the attacker takes over a valid [[TCP|TCP]] communication session between two computers. This can be done because most types of [[Authentication|authentication]] are only performed at the beginning of a TCP session, and a session can be hijacked while it is still in progress without authenticating.

Session hijacking exploits a session-token generation mechanism or token security controls so that the attacker can establish an unauthorized connection with a target server. The attacker can guess or steal a valid session ID, which identifies authenticated users, and use it to establish a session with the server. The server responds to the attacker's requests under the impression that it is communicating with an authenticated user.

Session hijacking can be a precursor to various types of attacks, including [[On-path attack|on-path/MITM]] attacks and [[DoS|DoS]] attacks.

![[Pasted image 20230210211511.png]]

