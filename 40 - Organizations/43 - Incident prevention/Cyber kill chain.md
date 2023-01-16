The cyber kill chain is a way of illustrating how an adversary can attack a target organization. The model helps organizations understand the various possible threats at every stage of an attack and the necessary countermeasures to those attacks. It also provides security professionals with a clear insight into the attack strategy used by the adversary.

There are seven different phases that are usually followed in an attack.

## Reconnaissance
This stage involves the collection of information to be used for attacks.

Actions of the attacker may include:
- Gathering information through the internet or through social engineering
- Performing analysis of online activities and other OSINT
- Scanning open ports and services
- Performing Whois, DNS, and networking foorprinting

## Weaponization
This stage involves using the information gathered and creating or reusing a weapon of some sort.

Actions of the attacker may include:
- Identifying appropriate malware to be used
- Creating a new malware payload or modifying an old one
- Creating a phishing email campaign
- Leveraging exploit kits and botnets

## Delivery
This stage involves delivering that weapon to the target.

Actions of the attacker may include:
- Sending phishing emails to employees
- Distributing USB drives with the payload to employees
- Performing attacks on a website such as a [[Watering hole|watering hole attack]]

## Exploitation
This stage involves using the weapon to exploit a vulnerability somewhere on the target system.

Actions of the attacker may include:
- Exploiting software or hardware vulnerabilities to gain remote access to the target system

## Installation
This stage involves downloading and installing more malicious software on the target system to maintain access to the target network for an extended period.

Actions of the attacker may include:
- Downloading and installing malicious software such as backdoors
- Gaining remote access to the target system
- Leveraging various methods to keep backdoors hidden and running
- Maintaining access to the target system

## Command and control
This stage involves the attacker creating a command and control channel, which establishes two-way communication between the victim's system and the adversary-ctronolled server in order to communicate and pass data back and forth.

Actions of the attacker may include:
- Establishing a two-way communication channel
- Leveraging channels such as web traffic, email communication, and DNS messages
- Applying privilege escalation techniques
- Hiding evidence of compromise using techniques such as encryption