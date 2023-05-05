Insecure direct object references (IDORs) are a type of access control vulnerability that arises when an application uses user-supplied input to access objects directly.

For a basic example, take the following URL:
`https://target.com/customer_account?customer_number=12345`
If there are no controls in place, an attacker could replace the `customer_number` with any other number to see the records of other customers. This is an example of IDOR that leads to horizontal [[Privilege escalation|privilege escalation]].

Sometimes, websites access resources in static files on the server-side filesystem. For example, a website might save chat messages in an incrementing filename, like so:
`https://target.com/static/12938.txt`
An attacker could change that number and try to find other message files.