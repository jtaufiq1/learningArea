# --[ INTRODUCTION - THE INTERNET & PROTOCOLS

## The Internet
Billions of network devices and networks connected together
using links and protocols to communicate.

* Networks: collection of devices, packet switches, links and managed by an individual or an organization.
A network can be:
	private or public network,
	home network or an enterprise network,
	wired or wirelessly connected,
	connected to a small/larger network(s) through an ISP's.

* Network devices (hosts|nodes|end systems)

* Communication links establishes physical connection between network entities or networks; Eg.: fiber optic cables, copper, radio, satellite and transmits bits in time (seconds)
Transmission rate: bandwidth = bit/second (bps).

* Packet switches forward packets (chunk of data); a packet switch can be a switch or a router depending on its functionality.
The internet as an infrastructure provide services to applications and provides API's the for communications.
Internet Service Providers connect networks together.

## Protocols & Standards
- defined rules, control sending and receiving of messages
- All communications are governed by protocols Eg: Ethernet 802.3, TCP, https, ftp, IP, WiFi, 4G etcs
- Standards: RFCs<--IETF

* Protocols:
	Defines format and order of messages, sent or received among network entities and actions taken on transmission and receipt.
	These protocols are standardized into RFCs by IETF.

- RFCs = Request for Comments
- IETF = Internet Engineering Task Force

## Network Edge
* Hosts or End devices
	client and servers are found at the edge of a network
	client are normally workstations, request service from servers
	servers often found in data centers, provides and serves client requests. client or server apps runs at the network edge.
	Eg: Mobile devices, Appliances, PC Workstations, and many more.

## Access Networks
Access networks are either wired or wireless communication links connecting hosts or end systems to an ISP network with a transmission rate (bps) and either shared or dedicated access among users connected to an ISPs' edge router. The 3 types of access networks are; 

### Residential Access Networks
* Cable-based access
	uses shared cable distribution network to tansmit data|TV
	transmits different channels in different frequency band ie FDM.
	transmission is asymmetric: downstream is higher than upstream
	downstream(40Mbps-1.2Gbps), upstream(30Mbps-100Mbps)
	Homes share access cable to headend and fiber at headend attaches homes to ISPs' edge router.


					[home]						     (Headend)
					  ||
	[home]-CM-Sp=====SC======SC======SC======SC=====|->[-CMTS=]
			  ||		  ||							  |
			[home]		[home]							  |
													-------------
													[Edge Router]


	RAN = Residential Access Network
	CM = Cable Modem
	Sp = Splitter
	SC = Shared Cable
	CMTS = Cable Modem Termination System
	FDM = Frequency Division Multiplexing
	HFC = Hybrid Fiber Coax
	ISP = Internet Service Provider

	NB: Homes in Residential Access Network have Cable Modem and a Splitter connected to a single shared cable to a terminator (headend). Headend attaches to ISP using fiber.
* Digital Subscriber Line (DSL)
	Uses existing telephone line to transmit voice/data at different frequencies over a dedicated line to central office DSLAM
	- Data over DSL phone line goes to the internet
	- Voice over DSL phone line goes to the telephone network
	Transmission is asymmetric with dedicated downstream transmission rate of 24~52Mbps and upstream transmission rate of 3.5~16Mbps.
	The transmission rate depends very strongly on the distance from the home to the central office.
	
* Institutional Access Networks
* Mobile Access Networks

## Network Core
