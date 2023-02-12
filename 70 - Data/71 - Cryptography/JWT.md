JWT, short for JSON Web Token, is a proposed internet standard that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. JWTs are small and can be sent through URLs, POST parameters, or inside an [[HTTP headers (recon)|HTTP header]].

The website jwt.io provides the basic encoding scheme.

The basic layout of JWT is split into three sections, divided by periods.
1. The header, which usually contains the algorithm and the token type, in this case JWT
2. The payload, which contains the actual data
3. The section to verify the signature