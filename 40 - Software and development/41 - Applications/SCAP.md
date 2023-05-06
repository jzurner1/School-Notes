Security content automation protocol (SCAP) is a suite of specifications for exchanging security automation information used to help organizations automate the way they monitor system vulnerabilities and make sure they're in compliance with security policies.

### Why?
SCAP provides administrators with the ability to scan network devices and software in order to detect anything that does not align with a predetermined security baseline. It uses a suite of specifications to standardize all the different terminology and formats, making it easier for administrators to keep their organization secure.

### Components
The two main components of SCAP are the SCAP content and the SCAP scanners.

SCAP content consists of modules that are freely available. They are developed by NIST and made from secure configurations. For example, the Federal Desktop Core Configuration is a hardened version of Windows.

SCAP scanners are tools used to compare a target device or application's current configuration with that of the SCAP content baseline. Any deviations will be added to a report. Some scanners can automatically reconfigure a device to meet the baseline. SCAP scanners can be either commercial or open-source, but they all have the same baselines.