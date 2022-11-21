User accounts tend to follow a particular life cycle:

![[Pasted image 20221120223504.png]]

1. When an account is first **approved** for creation, it's assigned to an identity and given authentication credentials. Vulnerabilities in this phase include accounts created without administrative oversight, accounts assigned to mistaken or non-trusted identities, and accounts with weak or no passwords/credentials. Attackers with temporary access can exploit this phase to create their own accounts.
2. Before use, the account must be **provisioned**, or assigned roles and privileges according to whatever [[Access control|access control]] model is used. It's easy to introduce vulnerabilities by assigning too many permissions to an account that may be abused or compromised later, so it's essential to use least privilege principles. Attackers can exploit provisioning for privilege escalation purposes.
3. Active accounts must be **maintained** actively. Administrators should periodically review account privileges, especially after the owner's roles or duties have changed. Since attackers will target active accounts, ongoing monitoring should watch for signed of misuse or suspicious activity.
4. When accounts are no longer needed, or when some of their roles are no longer needed, they should be disabled, deleted, or **deprovisioned**. Otherwise, they remain a security vulnerability.