# --[ INTRODUCTION TO INFORMATION SECURITY

## Information Security
Focuses on the protection of information and information systems from unauthorized access, tampering/manipulation or disruption.

* Elements of information security
- Confidenciality
- Integrity
- Availability
- Authenticity
- Non-repudation

* Reasons for information Security attacks
Attacks = Motives + Method + Vulnerability

- Disrupt services
- theft
- data manipulation
- cause fear and panic
- Recognition
- Hobby etc.

* Classification of Attacks:
- Passive
- active
- close-in
- insider
- Distribution

## Information Warfare
Information warfare is the use of ICT to gain competitive advantage.

- Defensive warfare: strategies used to defend attacks on ICT assets.
- Offensive warfare: involves attacks against ICT assets.

## The Four Point Process (OSSTMM)
The Four Point Process outlines 4 ways the basic interactions are used to analyze something as deeply as possible (Mess with it, watch it and observe the outcome).

The **FPP** has you look at interactions in the following ways:
* Induction
    What can we tell about the target from its environment? How does it behave in that environment?
    Is the target influenced by it environment? - if not, that's interesting too.
* Inquest
    What signals [emanations] does the target gives off? Investigate any tracks or indicators of those emanations.
    A system or process generally leaves a signature of interactions with its environment.
* Interaction
    What happens when you poke the target?
    This point calls for echo tests, including expected and unexpected interactions with the target to trigger responses [Cause-and-effect].
* Intervention
    How far will the target "bend" before it breaks?
    Intervene with the resources the target needs, like electricity, or meddle with it's interactions with other systems to understand the extremes under which it can continue operating.

## Cyber Kill Chain (CEH)
Intelligence-driven defense concept for identification and prevention of malicious intrusion activities.
Provides greater insights into attack phases

* Stages of Cyber kill Chain
- Reconnaissance: 
- Weaponization
- Delivery
- Exploitation
- Install Malware
- Command & Control (C2) operation
- Actions on Objectives (Goals)

** Tactics, Techniques, and Procedures (TTPs)
TTPs get at how threat agents manage and conduct attacks
The patterns of activities/methods associated with a specific threat actor or group of threat actors.

Analysis of TTPs aids in counter intelligence and security operations by answering how threat agents perform attacks.

Threat Hunting refers to proactively and iteratively searching through networks or datasets to detect and respond to threats that evade traditional rule- or signature-based security solutions.

It includes using both manual and machine-assisted techniques, and aims to find the Tactics, Techniques and Procedures (TTPs) of advanced adversaries.

*** Tactics
*** Techniques
*** Procedures

** Adversary Behavioral Identification
- Internal reconnaissance
- Use of power shell
- command line interface
- web shell
- HTTP user-agent
- Unspecified proxy activities
- Command and control
- DNS Tunneling
- Data Staging

** Indicators of Compromises (IoCs)
Pieces of forensic data, artifacts or clues that signifies malicious intrusion in a network or operating system

Information of suspicious activities gathered in a network establishment.

The atomic, computed or behavioral indicators of malicious intrusion.
Can be useful source of forensic evidence.

* Categories of IoCs
- Email Indicators
- Network Indicators
- Host-based Indicators
- Behavioral Indicators

## Information Security Controls
The basic security concept critical to information on the internet;
- Confidentiality
- Integrity and 
- Availability

Information Security Control prevents unwanted events and reduces risk to an information assets.

** Information Assurance (IA)
The Assurance that the integrity, availability, confidentiality and authenticity of information and information systems is protected during the usage, processing, storage and transmission of information.

Using physical, technical and administrative controls, Information Assurance and Risk Management (IRM) ensures that only authorized personnel access and use information.

Some process that help in achieving information assurance;
- Develop local policy, process and guidance
- Design network and user authentication strategies
- Identifying network vulnerabilities and threats
- Identifying problem and resource requirements
- Creating plans for identified resources requirements
- Applying apropriate IA controls
- Performing certification and accreditation
- Providing IA training

** Defense-in-Depth
Security strategy in which several protection layers are placed throughout an information system.
It prevents direct attacks against the system and its data. A break in one layer leads the attacker to the next layer.

It gives administrators and engineers time to deploy new or updated counter measures to prevent the recurrence of the intrusion.

* Defense-in-Depth Layers
^
|          Policies, Procedures and Awareness
|         Physical
|       Perimeter
|     Internal Network
|    Host
|  Application
|Data
+-------------------------------------------->

** Risk
The degree of uncertainty that an adverse effect may cause damage to the system or its resources under specified conditions.

- Probability of occurrence of a threat
- Damage, cause loss or negative impacts
- On the organization
- Either from internal or external liabilities

The likelihood that an event will occur and the impact the event might have on an IT assets.

Relation between Risk, Threats, Vulnerabilities and Impact
RISK = Threats * Vulnerabilities * Impact

Impact of an event on information asset to the stakeholders
RISK = Threat * Vulnerability * Asset Value 

* Factors of Risk
- The probability of the occurrence of adverse event
- The consequence of the adverse event

* Risk Level
The assessment of the resulted impact on the network. Risks are categorized into different levels according to their estimated impact on the system.
Level of Risk = Consequence * Likelihood

- Extreme/High
Serious or Imminent danger
Requires immediate measures to combact
Identify and impose control to reduce the risk to a reasonable low level.

- Medium
Moderate Danger
Immediate action not required but action should be implemented quickly
Implement control to reduce the risk to a reasonable low level.

- Low levels
Negligible danger
Take preventive measures to mitigate the effects of risk.
Control measures may limit the level of risk but do not always eliminate them completely.

* Risk Matrix 
Scales the risk occurrence along with its impact.
The graphical representation of risk matrix is used to visualize and compare risks.

Risk Matrix:
      Likelihood | Consequence
Scaling the risk by considering the probalility, likelihood and consequences or impact.
___________________________________________________________________
| Probability |  Consequences					  |
------------------------------------------------------------------|
                Insignificant | Minor | Moderate | Major | Severe |
             L
             i
             k
             e
             l
             i
             h
             o
             o
             d
|_________________________________________________________________|

* Risk Management 
The process reducing and maintaining risk at an acceptable level.
By means of well-defined and actively employed security progam, risk can be reduced and maintained at an acceptable level.

Phases of Risk Management
- Risk Identification:
    Identify sources, causes, impact and other details of internal and external risk affecting the security of the organization.
- Risk Assessment:
    Assesses the organization's risk and provide and estimates of likelihood and impact of the risk.
- Risk Treatment:
    Selects and implements controls for the identified risks.
- Risk Tracking & Review:
    Ensures apropriate controls are implemented to handle known risks and calculates the chances of new risks occuring. Evaluates the performance of the implemented management of risk strategies.

** Cyber Threat Intelligence (CTI)
The collection and analysis of information about threats and adversaries an the drawing of patterns that provide the ability to make knowledgeable decisions for preparedness, prevention, and response actions against various cyber-attacks.

CTI helps the organization to identify and mitigate various business risks by converting unknown threats into known threats; it helps in implementing various advanced and proactive defense strategies.

* Types of Threat Intelligence
- Strategic
    Higher level information on changing risks. Consumed by higher-level executives and managements.
- Tactical
    Information of attackers TTPs. Consumed by IT service, SOC managers and administration.
- Operational
    Information on a specific incoming attack. Consumed by security managers and network defenders.
- Technical
    Information on specific indicators of compromises (IoC) and consumed by SOC staff and IR (Incident Response) team.

** Threat Modelling
The risk assessment approach for analyzing the security of an application by capturing, organizing and analyzing all the information that affects the security of an application. It involves;
- Understanding the adversary's perspective
- Characterizing the security of the system and
- Determining threats.

* Threat Modeling Process
Series of steps followed to identify weakness related to an application.

1. Identify Security Objectives: determines the effort needed for the subsequent steps that follow.
2. Application Overview: Identify the components, data flow and trust boundaries
3. Decompose the Application: Helps find more relevant and detailed threats.
4. Identify Threats: Identify threats relevant to the control scenario and context using the information obtained in step 2 and 3.
5. Identify Vulnerabilities: Identify weakness related to the threat found using vulnerability categories.

** Incident Management
A set of predefined processes to identify, analyze and resolve security incidents to restore normal service operations as quickly as possible and prevent future recurrence of the incident.

Incident management include the following:
- Vulnerability analysis
- Artifacts analysis
- security awareness training
- Intrusion detection (Alerts)
- Public and Technology monitoring
- Incident Handling
   - Triage
   - Reporting and Detection
   - Incident Response
   - Analysis
- Other incident management services.

Incident management is designed to:
- Improve service quality
- Resolve problems proactively
- Increase staff effeciency and productivity
- Meet service availability requirements
- Improve user and customer satisfaction
- Assist in handling future incidents

Conducting training sessions to spread awareness among users is an important part of indident management.

* Incident Handling and Response
Incident Response is one of the functions performed in incident handling.
In turn, incident handling is one of the services provided as part of incident management.
Incident Response <- Incident Handling <- Incident Management Services

## Information Security Laws and Conducts