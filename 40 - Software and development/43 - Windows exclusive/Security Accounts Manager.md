[[Windows|Windows]] uses the Security Accounts Manager (SAM) database to manage user accounts and passwords in a [[Hashing|hashed]] format. The SAM database is implemented as a [[Windows registry|registry file]].

By default, passwords are stored at `%SystemRoot%/system32/config/SAM`, and it is mounted in the registry under the HKLM/SAM registry hive. It stores LM or [[NTLM|NTLM]] hashed passwords.

The SAM file stores passwords as follows:
`<username>:<user ID>:<LM hash>:<NTLM hash>`
For example:
`Bob:1004:NO PASSWORD******************:83AB78C03...`