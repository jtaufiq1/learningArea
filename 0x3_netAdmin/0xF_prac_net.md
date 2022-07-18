# PRACTICAL NETWORKING FUNDAMENTALS

## --[ INTRODUCTION
Network is group of devices connected together to communicate or share information.

## --[ NETWORKING DEVICES
* Node: A device that implements IP.

### Host
Host is node that sends or receive traffic. Eg: Computer, Printer, IoT devices etc.
Basically, any device that sends or receives IP packet is a host. Host in a network is either a client or server.

* Clients send requests to a server and servers respond to client's requests.
* Host acting as a client or server is relative to specific communication.
* Clients and servers have software installed on them for sending or responding to requests.
* A server can act as a client and a client can act as a server at an instance of communication.
* Host in a network have an identity known as IP address.

### Repeater
Data/signals decays as it travels through a wire (transmission medium). Repeaters help to regenerate signals as it travels.

### Hub
Connecting hosts directly to each other doesn't scale. Hub is simply a multi port repeater that facilitate scaling communication network.
Signals are sent to all nodes in a hub connected network.

### Bridge
A bridge is a device that sits between (two) hub connected networks. Bridges learn which hosts are on each side of the hub.

### Switch
A switch is the combination of a hub and a bridge or simply a multi port bridge. It learns which node is connected on each port.
It facilitate communication within a network.

### Router
A router is a device that separate networks and facilitate communication between them. Each interface on the router is a separate broadcast domain.
Routers learn which networks they are attached to and store it in a routing table.

Routing table contains the lists of networks a router knows about.
Routers have IP address on the networks they are attached to and serve as a gateway for each hosts in their local subnet.

## --[ IP ADDRESS
An IP address is the identity of a host in a network. An IP is a 32-bit binary number represented as 4 octets.
Each octet is in the range of 0-255. IP's create networks and hierarchy in the networks. Eg: 192.168.45.12

## --[ NETWORK
Network is the logical grouping of hosts that require similar connectivity. Network transport traffic between hosts.
A network contain other networks (subnet). A network may connect to other networks.

* Switching is the process moving data within a network using a switch.
* Routing is the process traffic between networks using a router.
* There are many other network devices:
	- Access points			- Layer 3 switches
	- Firewalls				- IPS/IDS
	- Load Balancers		- Proxies
	- Virtual switches		- Virtual Routers
All of them perform switching and/or routing.

## --[ OSI REFERENCE & TCP/IP MODEL
The main purpose of networking is to allow communication or sharing information between devices of different kinds.
Networking architectures provides set of instructions (models) for communicating a data across a network successfully.

These architectures defines the functions of the models in layers. Each layer perform a specific function using specific protocols associated to the layer.
Networking devices/nodes use their APIs and framework to perform the needed network function.
Types of networking architecture models are the old OSI reference & TCP/IP model.

### OSI REFERENCE MODEL
Open System Interconnection Model is a referrence model that standardizes network communication. It is the oldest model to reference network standards.
It describes and categorizes the functions of networking into 7 layers. Each layer serves a specific purpose/function in network communication process.

#### Layer 1 - Physical Layer
This layer defines the physical topology of the network and transport bits from source to the immediate connected node.
Bit Encoding: Converting digital raw bits into electrical, optical or radio signals which best suits the transmission media.
The main function of the physical layer is to transport bits between nodes.
Examples oflayer 1 technologies: Cables (coaxial, ethernet, fiber), hub, repeater.

#### Layer 2 - Data Link Layer
Data link layer interacts with the physical layer using Network Interface Card (NIC) or Network Access Card. It is concerned with the physical addressing of the NIC and the logical topology of the network.
The addressing scheme is a 48 bit hexadecimal number known as MAC address.
The Media Access Control (MAC) address represented as 12 hexadecimal digit uniquely assigned to every NIC. The Layer 2 facilitate hop to hop delivery of data.
Examples of layer 2 technologies: Bridge, NIC, Switch

#### Layer 3 - Network Layer
Layer 3 is concerned with the logical addressing of nodes using the IP (Internet Protocol). End to end delivery of data, flow control, forwarding decision.
Layer 3 technologies: Routers/Gateways, Hosts, Multilayer switch.

#### Layer 4 - Transport Layer
Distinguishes data streams using port numbers and facilitate service to service delivery of data. Port number is a 16-bit number (0-65535).
TCP and UDP are the primary transport layer protocols.

* TCP - Transmission Control Protocol favors reliability and a connection oriented protocol. Uses 3-way handshake to establish a connection. Uses unicast to deliver data.
* UDP - User Datagram Protocol is a connectionless protocol and favors effeciency using best effort to deliver data. Uses unicast, multicast, and broadcast to deliver data.

Layer 4 technologies: Hosts (Servers & clients), Layer 4 firewall.
	- Servers run software that listens on a predefined port and clients selects a random port for each communication.

#### Layer 5 - Session Layer
Establishing, maintaining and tearind-down a session is done at this layer in the OSI model.

#### Layer 6 - Presentation Layer
Defines standards for data formatting and encryption.

#### Layer 7 - Application Layer
Provides application services protocols and service advertisement using standardize protocols. Examples of application layer protocols: HTTP(S), DNS, SMTP, FTP etc.
Layer 7 technologies: Hosts, Layer 7 firewall. 

### TCP/IP MODEL
Transmission Control Protocol/Internet Protocol is the current networking architecture in practice.
It is a 4/5 layer Model. It combines layer 5,6 and 7 of the OSI reference model into one as application layer.
Hosts communicating on the internet implements set of protocols using TCP/IP suite

#### APPLICATION, PRESENTATION & SESSION LAYER
Top most layer of the internet protocol stack. Combines functions of the application, session and presentation layer of the OSI reference model.

* Application, protocols and services that interface with the end user.
* Data formatting, conversion, encrypted/decrypted, compressed/decompressed and sent or presented to the user (MIME Types)
* Opens/Closes and manage a session between end-user application processes using RPC.
* Application layer protocols are divided into 2 categories:
	- User protocols: FTP, SMTP/POP, SSH etc.
	- Support protocols: SNMP, DNS, DHCP etc.

#### TRANSPORT LAYER 
Provides end-to-end (E2E) communication services for applications.

* Multiplexing: End-to-End communications between multiple applications (processess) simultaneously using (ports).
* Reliable and unreliable end-to-end data transport and data stream services.
* Connection oriented, connectionless communications and data stream services (Session establishement and termination).
* Data is broken up into segments, adds a header with source and destination port number.
* TCP and UDP are the primary protocols at this layer:
	- TCP is a reliable connection oriented transport service. E2E reliable transmission, sequencing and flow control.
	- UDP is connectionless datagram transport service that favors efficiency.

#### NETWORK/INTERNET LAYER
Internet transport protocols use IP to carry data from source host to destination host.
It is a connectionless or datagram internetwork service with no E2E delivery guarantee. IP provides logical addressing of hosts, fragmentation, type of service specification information security.

* Provide host addressing (IP).
* Routing: Choosing the best path to the destination network
* Forwarding: Switching packets out of the correct interface.
* Maintain quality of service (Qos).
* Connectionless end-to-end networking and flow control.
* Segments is broken up into packets/datagram and IP header is added with source and destination address.
* Protocols at the network layer: IP, ICMP, IGMP.

#### DATA LINK/NETWORK ACCESS LAYER
Communication protocols used to interface the network directly connected. Also known as the media access layer. Wide variety of link layer protocols exists for different types of networks.

* Divided into 2 sublayers.
* Logical Link Control (LLC, 802.2) sublayer provides services to the upper layer and synchronization control.
* Media Access Control sublayer defines how devices access the medium (CSMA/CD, CSMA/CA, Token passing).
* Defines the logical topology of the network (Ethernet, Token ring etc).
* Host addressing (MAC Address).
* Adds layer 2 header (frame) with source and destination MAC address.
* Error checking mechanism using Frame Check Sequence (FCS).
* Converts data to signals appropriate to the transmission medium.
* Protocols at the link layer: Ethernet, Token ring etc.

### DATA ENCAPSULATION & DE-ENCAPSULATION
Networking architecture models use set of instructions for data communication across a network successfully. Each layer of the model has specific function.
Each layer uses specific protocols and standards associated to the layer. Network hosts/nodes use the network models API's and framework to determine what is needed.

* Communicating entities use a protocol to communicate with same layer on another hosts.
* On a single system, one layer provides a service to a higher layer. A layer requests a lower layer to perform a needed function.

#### ENCAPSULATION
Terms used to describe the headers for data encapsulation process at each layer of the TCP/IP model.
- Data: Layer 1 Protocol Data Unit (PDU) (Application layer)
- Segment Layer 2 PDU (Transport layer)
- Packet / Datagram (Network Layer)
- Frame Layer 4 PDU (Link layer)

* The application layer protocol data unit (PDU), data is passed down to the next layer.
* The transport layer breaks down the application layer PDU into segments, adds header to each segment.
* The network layer breaks segments into packet and adds header containing source and destination address.
* The link layer adds frame with source and destination MAC address to each segment with an optional trailer.
* Frames are converted to signals appropriate to the transmission medium and forwarded.

#### DE-ENCAPSULATION
The reverse of encapsulation as data moves up the networking stack, stripping each layer's header off.

#### TCP/IP and OSI REFERENCE MODEL

+=======================================================================================+
| 									**NETWORK ARCHITECTURE**							|
+---------------------------------------------------------------------------------------+
|	  OSI		|	TCP/IP 		|	PDU		| 				 PROTOCOLS					|
+---------------------------------------------------------------------------------------+
| Application 	| Application 	| 			| HTTP(S), DNS, SMTP, POP, SSH, NTP,		|			^
+---------------+				|			| TLS/SSL, Telnet							|			|
| Presentation 	| 				| Data		|											|			|
+---------------+				|			|											|	|		|
| Session		| 				|			|											|	|
+---------------+---------------+-----------+-------------------------------------------+	|	*[ De-Encapsulation ]*
| Transport 	| Transport 	| Segment	|				TCP, UDP					|	+		|
+---------------+---------------+-----------+-------------------------------------------+	|		|
| Network 		| Network 		| Packet    | IP, ICMP, IGMP, IPSec						|	|		|
+---------------+---------------+-----------+-----------------------\[ARP\]-------------+	|		^
| Data Link 	|	Network		| Frame		|											|	|		|
+---------------+  	Access		+-----------+ MAC, PPP,	Ethernet 802.3					|*[ Encapsulation ]*
| Physical 		| 	Layer 		| Bits		| 802.11 Wireless, SONET/SDH 				|	|->>>>--+
+---------------------------------------------------------------------------------------+

## --[ HOST COMMUNICATION
Host in a network must be configured with 4 basic settings in order to communicate in the network.
IP Address: Identity of the host in the network
Subnet mask: Defines hosts Local Network range
DNS: Resolves domain names to IP address
Gateway: Host way of communication in foreign network.

For a host to communicate with another host in the Local Network or foreign network. It must;
* Identify the hosts' IP address either manually or automatically using DNS.
* The hosts' networking stack fills all the appropriate fields (encapsulation).
* If destination host is in the local network, the data is forwarded to the hosts' MAC address resolved using ARP.
* If the destination host is on a foreign network, the data is forwarded to the hosts' gateway MAC address for routing.

## --[ SWITCH OPERATION (SWITCHING)
A switch is a layer 2 device and it's primary purpose is to facilitate communication within a network.
Devices communicating through a switch belong to the same IP subnet. Switch makes decision based on MAC address.
A switch use/maintain MAC address table. The MAC address table contains a mapping of switch port to MAC address.

A switch perform 3 actions to populate/update the MAC address table.
i.e. Learning, Flooding and Forwarding to update its MAC address table.

1. Learn: A switch updates its MAC address table with mapping of switch port to source MAC address.
2. Flood: A switch duplicates and sends frame out on all its ports except the initial receiving port.
3. Forward: A switch forward frame to the appropriate switch port based on it MAC address table.

### MAC Address Table
+---------------------------------------------------+
| 	SWITCH PORT		|		MAC ADDRESS				|
|-------------------+-------------------------------+
|					|								|
+-------------------+-------------------------------+
|					|								|
+-------------------+-------------------------------+
|					|								|
+-------------------+-------------------------------+
|					|								|
+-------------------+-------------------------------+

* Updating the MAC address table is identical even if the host/node is a gateway/router connected to other networks.
* A switch has a MAC address and configured with an IP which essentially acts as a host in the network.
* A switch MAC and IP address is only used if a traffic is destined to the switch.
* Address Resolution Protocol (ARP) links/resolves layer 2 MAC address to layer 3 IP address.

## --[ TYPES OF DATAGRAMS (UNICAST, BROADCAST AND MULTICAST DATAGRAMS)
A datagram is the basic unit of transmission in a data network.

* UNICAST DATAGRAM: A datagram from one device/node destined to another node within/outside a network.
* BROADCAST DATAGRAM: A datagram from one device to all other devices within the same subnet or network segment.
* MULTICAST DATAGRAM: A datagram from one device to a set of devices in a multicast group. Devices in multicast group listen for multicast datagram 

## --[ ROUTING
Routing is the process of forwarding packets/datagram to the appropriate interface.

## --[ PROTOCOLS








