--[ Introduction - Computer networking
 * Group of computers (nodes) connected to communicate, share data/resources together.
 * Uses a set standards (protocol) to communicates to each other.
 * The connection can within a small area or can span a large geographical area.
  - Local Area Network (LAN)
  - Wide Area Network (WAN)
  - Personal Area Network (PAN)
  - Metropolitan Area Network
 * The Internet (inter-networks) is the interconnection different networks from/in different locations to share and communicate.

--[ TCP/IP Five-Layer Network Model
 * Transmission Control Protocol/Internet Protocol is a five-layered network model.
 * Provides framework for transmitting data and requires basic information to transmit the data in a network.
 * Each layer in the TCP/IP stack serves the layer above it and it is served by the layer below it.
 * TCP/IP Layer Stack
  - Application Layer (layer 5 Applications that communicates to remotely. Eg: Web Browsers, email clients etc. protocols: http/s, ftp etc. PDU: message)
  - Transport Layer (layer 4 Establish connection btn remote host. protocols: TCP/UDP. PDU: segment/datagram. Ensures that data gets to the right application)
  - Network Layer (layer 3 Allows different networks to communicate using routers. protocol: IP. PDU: packet)
  - Data Link Layer (layer 2 creates frames, uss MAC address locate host in LAN. protocols: Ethernet, Wi-fi)
  - Physical Layer (layer 1 The Physical devices and Transmits bit between devices.)

--[ The Basics of Networking Devices
 * Cables: connects different devices using wires (copper/optic)
  - Cat5, Cat5e, Cat6
  - Fiber Optics: uses pulses of light to transfer data.
 * Hubs and Switches
  - Hubs: allows many devices to connect. Collision Domain very common
  - Switches: Layer 2 devices and its smarter than hub
 * Routers
  - Layer 3 devices. Forwards data between independent networks. Contains routing table. Forward traffic from a node to the ISP.
  - Routers share data using Border Gateway Protocols (BGP).
 * Servers and Clients
  - Clients: Clients sends request to servers.
  - Servers: serves data to clients or responds to client requests.

--[ The Physical Layer
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

--[ The Data Link Layer
 * Ethernet and MAC addresses
  - Ethernet is most common protocol for sending data and it operates at the data link layer. It abstracts the network device used in the physical topology.
  - MAC addresses is 48-bit hexadecimal number used to identify a network interface. normally represent by six groupings of two hex numbers.
  - 

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