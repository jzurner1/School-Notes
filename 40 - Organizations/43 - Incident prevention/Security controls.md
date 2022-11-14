Security controls are tools and measures used to achieve security goals. It can be anything that protects your assets such as a network firewall, locks on a door, and a company policy on data backups. They are used to address each concern of the CIA triads.

# Categories
### Functional
There are four categories for a security control's functional nature.
- **Managerial**: Also known as administrative controls, these represent organizational policies and training regarding security. Management controls define the other control types in use by an organization, so they're the starting point for implementing security. Common management controls include password policies, employee screening, training procedures, and compliance with legal regulations.
- **Technical**: Technological solutions used to enforce security, sometimes also called logical controls. Technical controls include firewalls, authentication systems, and encryption protocols, among others. In modern data systems, technical controls do a lot of work and require the most exact knowledge, but they're only effective in conjunction with human activities used to implement and enforce them.
- **Operational**: Day-to-day employee activities which are used to achieve security goals. These are often defined by policies but exist in the effective execution of secure practices. Operational controls include backup management, security assessments, and incident response.
- **Physical**: Methods used to guarantee the physical security and safety of organizational assets. Physical controls can include locks, fences, video surveillance, and security guards.

### When it acts
Security controls can also be categorized based on when they act. Some security systems can work on multiple levels, such as a security camera being detective and deterrent.
- **Preventative**: Proactive controls which act to prevent a loss from occurring in the first place. Preventative controls include locked doors, network firewalls, and other policies to prevent intrusion and minimize vulnerabilities. Ideally, they would work well enough that the other types could be ignored.
- **Detective**: Monitoring controls that either detect an active threat as it occurs or record it for later evidence. Either way, it is primarily used to notify security personnel who can take preventative or corrective measures rather than securing assets themselves. This may include security cameras, network logs, auditing policies, and physical or network alarms.
- **Corrective**: Follow up controls used to minimize the harm caused by a security breach and to prevent recurrence. This can include restoring data from backups, changing compromised passwords, and patching vulnerable systems. Ideally, this will leave a system more secure than it was before the threat occurred.
- **Deterrent**: Visible controls designed to discourage attack or intrusion, especially in physical security. A "no trespassing" sign and the visibility of a camera may convince passive attackers from doing anything. This also includes disciplinary policies or training used to discourage employees from ignoring good security practices out of convenience.

# Confidentiality controls
Many of the most effective confidentiality controls are policy-based as opposed to technological. Reducing the exposure of data does a good job of keeping it out of the wrong hands.

- **Least privilege**: Users are only given the permissions they need to perform their actual duties.
- **Need-to-know**: Similar to least privilege but focused on restricting data access to those who require it. This includes restricting who can access a particular sort of data in the first place and restricting them to the data that they need within that data.
- **Separation of duties**: Breaking critical tasks into components, each of which is performed by a different employee with different permissions. While it does involve more people in the handling of sensitive information, it reduces the damage that any single employee can do.

- **Access controls**: Restricting access to systems and other resources, typically utilizing passwords, smart cards, or other authentication methods. This not only prevents unauthorized access but also enforces user permissions for authorized users and log activity for later review.
- **Encryption**: The use of mathematical processes to render data unreadable to those without the proper decryption key.
- **Steganography**: The practice of concealing a secret message in a more ordinary message, such as a hidden watermark to show a document's origin should it be stolen or copied. The hidden message may be encrypted as well, or at least be hard to discover.

# Integrity controls
Even if data isn't confidential, it needs to be protected from unauthorized deletion or changes, either by an attacker or unintentionally through an error or a user mistake.

- **Hashing**: Mathematical functions designed to create a small, fixed-size fingerprint of a given message or file, such that any small change in the original data will produce an entirely different hash. A hash may be used just to protect against data changes but it may also be used to prevent malicious modifications.
- **Digital signatures**: A combination of hashing and other cryptography that can be used to verify the authenticity of a message's creator as well as its integrity. Digital signatures can be used to create digital authentication tools called certificates.
- **Backups**: Backups are useful in the event that data is changed or deleted. The more frequent data is backed up, the more useful the backup will be.
- **Version control**: Storing multiple versions of files meant for frequent and collaborative changes such as documents, code repositories, and other collections of documents. It will automatically track changes and allow easy reversion to the original state.

# Availability controls
No matter what organization you are a part of, it is vital that data is available when it is needed.

- **Redundancy**: Multiple systems or backups configured so that if one fails, others can take its palce immediately or at least more quickly than the original can be repaired. This can include multiple identical servers able to perform the same function, backup systems that can be quickly brought online, or even entire backup sites in the event of a natural disasters. Redundant systems will usually have automatically triggered failover features.
- **Fault tolerance**: A system designed to continue functioning if a hardware or software component fails. Often this is done using redundant components such as RAID storage using multiple redundant disks so that if one fails, it can be replaced without data loss or interruptions.
- **Patch management**: When patches are applied, it is important to make sure that they don't interrupt system availability too much. Some patches knwon as hotfixes can be applied with little or no downtime, but most should be done in scheduled downtimes during low usage periods.