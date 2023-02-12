Session IDs are a method for applications to identify sessions, specifically in stateless communication protocols such as HTTP.

There are a few common methods to obtain session IDs:
- **Stealing** - This usually involves [[Wireless sniffing|sniffing]] of some form to sniff the traffic between a client and server to extract the session IDs from the packets. Alternatively, this could involve physical access such as acquiring the files containing session IDs or memory content's of the user's system or the server.
- **Guessing** - If the template for a session ID is short enough, it may be possible to guess. This is only useful for weak or flawed session ID generation mechanisms.
- **Brute forcing** - Similar to guessing, but with some form of pattern. This is useful when the algorithm produces session IDs that aren't random. If the predicted range of values for a session ID is small, this is known as a **session prediction attack**

Specific attacks that can compromise a session token include:
- Session sniffing
- [[Session replay|Session replay]]
- Predictable session tokens
- Session fixation
- [[On-path attack|On-path/MITM]]
- [[CRIME|CRIME]]
- [[Man-in-the-browser|Man-in-the-browser]]
- Forbidden attack
- [[XSS|Cross-site scripting]]
- Session donation
- [[CSRF|Cross-site request forgery]]