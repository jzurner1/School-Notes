A penetration test is an active and intrusive test to find threats in a system.

The goal of a penetration test is to verify that a theoretical threat exists.

# Ethics

### Rules of engagement
First of all, it is important that the rules of the penetration test are laid out before the testing begins. That is the responsibility of the , which should be established before the testing begins.

# Steps
Because of the variety of penetration test types, different steps may be required for different targets.

### General steps
Most penetration test methodologies follow the same general stages:
1. **Information gathering**: Collecting as much publicly accessable information about a target as possible using OSINT and recon.
2. **Enumeration/scanning**: Discovering applications and services running on the systems, such as web server versions that could be exploited.
3. **Exploitation**: Leveraging vulnerabilities discovered on a system or application.
4. **Privilege escalation**: Attempt to expand your access to a system by escalating horizontally or vertically, where horizontally is accessing another account of the same permission group and vertically is an account of another permission group.
5. **Post-exploitation**: Pivoting, gathering more information, covering tracks, and reporting.

### Other frameworks
There are a number of other penetration testing frameworks. Those include frameworks by OSSTMM, OWASP, NIST, NCSC, and so on.

# Types
Penetration tests can be categorized based on multiple characteristics.

### Amount of knowledge
- **Black box**: The tester is given no information about the inner workings of the application or service. They are effectively a regular user testing the functionality and interaction of the application or piece of software. This type of testing greatly increases the amount of time on the information gathering and enumeration/scanning steps.
- **Grey box**: The most popular type, the tester will have limited knowledge of the internal components of the application or piece of software. They will still be treated as a regular user. This type of testing reduces the amount of time required for information gathering and enumeration/scanning, so it is usually for well-hardened attack surfaces.
- **White box**: Generally this involves a software developer testing the internal components of the software. The tester will have full knowledge of the application and its expected behavior. This is the most time-consuming type of test.