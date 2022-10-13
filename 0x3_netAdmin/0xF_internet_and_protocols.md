# --[ INTRODUCTION - THE INTERNET & PROTOCOLS

## The Internet
Billions of network devices and networks connected together using links and protocols to communicate.

* Networks: collection of devices, packet switches, links and managed by an individual or an organization.
A network can be:
	private or public network,
	home network or an enterprise network,
	wired or wirelessly connected,
	connected to a small/larger network(s) through an ISP's.

* Network devices (Hosts|Ndes|end systems)
- computing devices such as PCs, Linux Workstations and Servers, Laptops, smartphones, IoT devices etc.
* Types of Networks
	Mobile Networks
	Home Networks
	Enterprise Network
	Global/Regional/Local ISPs

* Communication links establishes physical connection between network entities or networks;
	Eg.: fiber optic cables, copper, radio, satellite and transmits bits in time (seconds)
Transmission rate: bandwidth = bit/second (bps).

* Packet switches forward packets (chunk of data); a packet switch can be a link layer switches or a routers depending on its functionality.
	- Link Layer switches is typically used in access networks
	- Routers are typically used in network core
	- Route/Path is sequence of communication links and packet switches traversed by a packet from source to destination through a network.
	- Packet-Switched networks transport packets

* End systems are connected together by a network of communication links and packet switches.
	- End systems access the internet through an ISP
* An ISP is a network of packet switches and communication links. ISPs connect networks together.

* The internet as an infrastructure provide services to applications and provides API's the for communications.
	- Runs distributed applications that exchange data multiple systems. Eg: Video conferencing, Music Streaming, online social networks, multi-person games etc.

* End systems, packet switches and other pieces of the internet run protocols that control the sending and receiving information within the internet.
* End systems provide a _socket interface_ that specifies how a program delivers data on the internet infrastructure.
	- The interface is a set of rules followed by the sending host to the destination host.

* Transmission Control Protocol and Internet Protocol (TCP/IP) are the most important protocol on the internet.

### Protocols & Standards
* Protocols allow people to create systems and products that interoperate
* Defines the rules for controlling and sending of messages (information)
* IETF develop and maintain the internet standards. These protocols are standardized into RFCs by IETF.
	- RFCs = Request for Comments
	- IETF = Internet Engineering Task Force

* Protocols:
	Defines format and order of messages, sent or received among network entities and actions taken on transmission and receipt or other event.
* All internet communications are governed by protocols Eg: Ethernet 802.3, TCP, https, ftp, IP, WiFi, 4G etcs
* Different protocols are used to accomplish different communication task 

## Network Edge
* Hosts or End devices
	- End systems are referred to as hosts because they (host) run network applications.
	- Network apps include web browsers|server, email clients|server etc.
	- Hosts are divided into 2 categories: clients and servers
	- client and servers are found at the edge of a network
	- client are normally workstations, request service from servers
	- Servers often found in data centers, provides and serves client requests.
	- Eg: Mobile devices, Appliances, PC Workstations, and Linux box, and many more.

### Access Networks
Access networks are either wired or wireless communication links connecting end systems to an ISP network with a transmission rate (bps) and either shared or dedicated access among users connected to an ISPs' edge router.
The 3 types of access networks are:

* Residential Access Networks

** Cable-based access
	uses shared cable distribution network to tansmit data|TV. Connects multiple homes to a single cable headend.
	transmits different channels in different frequency band ie FDM. Transmits different signals in different frequencies
	Different frequencies do not interfere with each other	
	transmission is asymmetric: downstream is higher than upstream
	downstream(40Mbps-1.2Gbps), upstream(30Mbps-100Mbps)
	Homes share access cable to headend and fiber at headend attaches homes to ISPs' edge router.
```
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

	NB: Homes in Residential Access Network have Cable Modem and a Splitter connected to a single shared cable
	to a terminator (headend). Headend attaches to ISP using fiber.
```
** Digital Subscriber Line (DSL)
	Uses existing telephone line to transmit voice/data at different frequencies over a dedicated line to central office DSLAM
	- Data over DSL phone line goes to the internet
	- Voice over DSL phone line goes to the telephone network
	Transmission is asymmetric with dedicated downstream transmission rate of 24~52Mbps and upstream transmission rate of 3.5~16Mbps.
	The transmission rate depends very strongly on the distance from the home to the central office.
	
* Institutional Access Networks
* Mobile Access Networks

## Network Core
