The OWASP organization specifies the top 10 vulnerabilities and flaws of web applications. Below is a list of the current largest risks, last updated in 2021.

1. Broken access control - 94% of applications tested had some form of broken access control
2. Cryptographic failure - Previously known as sensitive data exposure, it has been refocused towards cryptography instead of the symptom of data exposure
3. [[Injection attacks|Injection]] - Again, 94% of applications tested had some form of injection vulnerability
4. Insecure design - A new category, this includes different weaknesses that can be expressed as "missing or ineffective control design"
5. Security misconfiguration - 90% of applications tested had some form of security misconfiguration; now includes the former XML External Entities (XXE) category
6. Vulnerable and outdated components - Previously known as "Using components with known vulnerabilities"
7. Identification and authentication failures - Previously broken authentication, now includes CWEs that are more related to identification failures
8. Software and data integrity failures - A new category, focusing on making assumptions related to software updates, critical data, and CI/CD pipelines without verifying integrity
9. Security logging and monitoring failures - Previously "Insufficient logging and monitoring;" can be difficult to test for
10. Server-side request forgery (SSRF) - Relatively low incidence rate with above-average testing coverage, but can be exploited easily