An advanced persistent threat (APT) is a type of network attack where an [[Attackers|attacker]] gains unauthorized access to a target network and remains in the network without being detected for a long time.

Some key characteristics of APTs include:
**Objectives** - Usually to repeatedly obtain sensitive information by gaining access to the organization's network. Also may be to spy for political or strategic goals.
**Timeliness** - The time taken by an attacker from assessing the target system for vulnerabilities to exploiting them to gain and maintain access to the target system.
**Resources** - The amount of knowledge, tools, and techniques require to perform an attack. APT attacks are more sophisticated than other attacks and are performed by skilled attackers.
**Risk tolerance** - The level up to which the attacker remains undetected in the target network. APT attacks are well planned and executed with proper knowledge of the target network, allowing them to remain undetected for a long time.
**Skills and methods** - Can vary significantly, possibly involving [[Social engineering|social engineering]] and detection prevention methods.

# Lifecycle
1. **Preparation**
	- Defining the target
	- Performing extensive research
	- Organizing a team
	- Building/obtaining tools
	- Performing tests for detection
2. **Initial intrusion**
	- Phishing, exploiting vulnerabilities, etc.
	- Launching further attacks on the network
	- Initiating an outbound connection
3. **Expansion**
	- Expanding access to the target network
	- Obtain administrative login credentials
		- Cached credentials
	- Alternatively, other methods
		- Social engineering
		- More vulnerablities
	- Difficult to track once logged in as administrator
	- Installing persistence mechanisms
	- Identify systems that can be leveraged for data exfiltration
4. **Persistence**
	- Maintaining access to the target
	- Customized malware
		- Designed to not be detected by antivirus software or security tools
		- Includes services, executables, and drivers
		- Locations that aren't frequently examined, such as printers, routers, servers, etc.
5. **Search and exfiltration**
	- Gaining access to a resource that can be used for further attacks or has value
	- Sometimes not aware of data location, so steal it all
	- Also use automated tools like network sniffers
	- Use encryption techniques to evade [[Data loss prevention policy|DLP]] technologies
6. **Cleanup**
	- More actions to prevent detection
	- Remove evidence of compromise
	- Make the system appear as it was before access was gained