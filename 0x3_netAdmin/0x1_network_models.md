## NETWORKING MODELS 1
The main purpose of networking is to allow communication or sharing information between devices of different kinds.
Networking architectures provides set of instructions (models) for communicating a data across a network successfully.

These architectures defines the functions of the models in layers. Each layer perform a specific function using specific protocols associated to the layer.
Networking devices/nodes use their APIs and framework to perform the needed network function.
Types of networking architecture models are the old OSI reference & TCP/IP model.

### OSI Reference Model
The main purpose of networking is to allow hosts to share data/resources. In order for that to happen effectively, the hosts involved must
follow a set of rules (protocols).

One of the networking models is the Open Systems Interconnection (OSI) Reference Model. It is a referrence model that standardizes network communication into 7 layers. Each layer performing specific function in the communication process.
It is the oldest model to reference network standards.
Each layer serves a specific purpose/function in network communication process.

### TCP/IP Model
Transmission Control Protocol/Internet Protocol is the current networking architecture in practice.
It is a 4/5 layer Model. It combines layer 5,6 and 7 of the OSI reference model into one as application layer.
Hosts communicating on the internet implements set of protocols using TCP/IP suite.
* Transmission Control Protocol/Internet Protocol is a five-layered network model.
* Provides framework for transmitting data and requires basic information to transmit the data in a network.
* TCP/IP Layer Stack
	- Application Layer (layer 5 Applications that communicates to remotely. Eg: Web Browsers, email clients etc. protocols: http/s, ftp etc. PDU: message)
	- Transport Layer (layer 4 Establish connection btn remote host. protocols: TCP/UDP. PDU: segment/datagram. Ensures that data gets to the right application)
	- Network Layer (layer 3 Allows different networks to communicate using routers. protocol: IP. PDU: packet)
	- Data Link Layer (layer 2 creates frames, uss MAC address locate host in LAN. protocols: Ethernet, Wi-fi)
	- Physical Layer (layer 1 The Physical devices and Transmits bit between devices.)

==============================================
The Physical Layer
  * Moving Bits across the wire: consist of devices that transmits bit across the network devices.
   - bit is the smallest representation of data a computer can understand. it is either 1 or 0. transferred using modulation.
   - Modulation is the way of varying the voltage of discharge across the cable known as Line Coding.

  * Twisted Pair Cable: Most type of cable to connect network and allows for duplex communication.
   - Duplex communication is a way of communicating in both direction
    - Full duplex allows communication in both direction at the same time.
    - Half duplex allows one communication at a time.
   - Simplex opposite of Duplex where communication is in one direction only.
  
  * Network Ports and Patche Panel
    - Most common network port is RJ45 
    - Patch panel device contain many ports

The Data Link Layer
 * Ethernet and MAC addresses
  - Ethernet is most common protocol for sending data and it operates at the data link layer. It abstracts the network device used in the physical topology.
  - MAC addresses is 48-bit hexadecimal number used to identify a network interface. normally represent by six groupings of two hex numbers.

 * Unicast, Multicast and Broadcast
  - Unicast is transmission meant for one address
  - Multicast is sent to all device in a network and get discarded 
  - Broadcast

 * Dissecting the Ethernet frame
  Highly structured collection of information presented in 
   - Preamble - 8 bytes, alternating 1s and 0s, SFD preamble is over.
   - Destination MAC 48 bits
   - Source MAC
   - EtherType field
   - VLAN header
   - Payload - Actually data being transport
   - FCS - 4-byte checksum calculated using CRC 

