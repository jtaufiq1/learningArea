# --[ CYBER KILL CHAIN
A detailed plan of defense and prevention of intrusion activities. The stages in Cyber Kill Chain are;
	* Reconnaissance:
		Information gathering on target - Organization, systems and users.
		- Public information
		- Organization information
		- Network information
		- Systems information
		- Specific IP's and Employees information
		- Monitoring and analyzing target's website
		- Whois, DNS and Network footprinting
		- Scanning to Identify open ports and services.
	* Weaponization:
		- Using gathered information to find vulnerabilites to exploit the target.
		- Creating exploit based on target vulnerabilities. Exploit are tailored to targets after analyzing the information gathered.
	* Delivery:
		- Using various techniques such as phishing, drive-by downloads, rogue USB drives etc to send exploit to the target.
		- Developing and performing several attack methods.
	* Exploitation:
		- Running malicious code on the target system to exploit vulnerability.
		- The target may face Authentication & Authorization Attacks, Security misconfiguration, Physical threat or Arbitrary code execution to exploit the target software/hardware to gain [remote] access.
	* Installation
		- Malicious softwares are installed on the target systems to maintain access.
		- Spread to other systems on the network
		- Hiding malicious activities.
	* Command & Control (C2|C&C)
		- Establish two-way communication channel between adversary control server and victims system.
		- Applying privilege escalation techniques.
		- Hiding evidence of compromise using techniques such as encryption.
	* Actions on Objectives (Goals)
		- Controlling target system(s) from remote location
		- Gaining access to confidential data
		- Distrupting of service(s)
		- Launch point to perform other attacks

## TACTICS, TECHNIQUES and PROCEEDURES (TTPs)
	Patterns of activities and method associated with specific threat actor or group of threat actors.
	Very useful for analyzing threat and profiling threat actors. And can be used to strengthen security.

	* Tactics:
		The guidelines that describes the way an attacker performs attacks and mode of operation(s) in different stages of the attack.
		From tactics for gathering information to initial exploitation, Privilege escalation, lateral movement and measures to ensure persistent access to the systems and other purposes.
	* Techniques:
		Technical methods and tools used to achieve intermediate results.
		Initial exploitation, setting up C2 channels, accessing targets infrastructure, data exfiltration and covering of tracks on targets systems.
	* Procedures:
		Sequence of actions carried out by threat actors at different stages in an attack life cycle. Such procedures differs by threat actors and objectives behind the attack.

		And it becomes more sophisticated when done by an APT (Advanced Persistent Threat) group.

## ADVERSARY BEHAVIORAL IDENTIFICATION
	Identification of common methods or techniques used by adversary to attack or penetrate an organization's network/system(s).

	Such identifications gives security professionals insight on upcoming threat and exploits.
	And aids in planning network security and adapting range of security measures as means of preventing various cyber attacks. Some activities include:
		* Internal Reconnaissance
		* Use of Powershell
		* Unspecified Proxy Activities
		* Use of command-Line Interface
		* HTTP User Agent
		* Command and Control Server
		* DNS Tunneling
		* Use of Web Shell
		* Data Staging

## INDICATORS of COMPROMISE (IoCs)
	IoCs are the clues, artifacts or pieces of forensic data that indicates potential intrusion in a network or operating system in an organization.

	They acts as good source of information regarding a threat. Continuous monitoring of IoCs effectively and efficiently detects and respond to evolving cyber attacks.

	* Groups of IoCs
		- Network Indicators
		- Email Indicators
		- Host-based Indicators
		- Behavioral Indicators

	* Key IoCs
		- Unusual outbound network traffic
		- Unusual activities through a privilege user account
		- Geographical anomalies
		- Multiple Login failures
		- Increased database read volume
		- Multiple request for the same file size
		- Mismatched port-application traffic
		- Suspicious registry or system file changes
		- Unusual DNS requests
		- Unexpected patching of systems
		- Signs of DDoS activities
		- Bundles of data in the wrong places
		- Web traffic with superhuman behavior