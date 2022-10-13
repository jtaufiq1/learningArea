# --[ NETWORKING MODELS
The main purpose of networking is to allow communication or sharing information between devices
of different kinds. Networking architectures provides set of instructions (models) for communicating
a data across a network successfully.

These architectures defines the functions of the models in layers. Each layer perform a specific
function using specific protocols associated to the layer.

Networking devices/nodes use their APIs and framework to perform the needed network function.
Types of networking architecture models are: OSI reference, DoD Model & TCP/IP model.

## OSI Reference Model
One of the networking models is the Open Systems Interconnection (OSI) Reference Model.
It is the oldest model that standardizes network communication into 7 layers.
It categorizes the function of networking into layers.
And each layer performs specific purpose/function in network communication process.

### Layer 7: Application Layer
Application services using protocols Eg: HTTP(S), DNS, BGP etc.
Service advertisement

### Layer 6: Presentation Layer
Data formatting and encryption

### Layer 5: Session Layer
Establishing, maintaining adn tearing-down a session

### Layer 4: Transport Layer
Transmission Control and User Datagram Protocols

  * Transmission Control Protocol (TCP)
    Reliable connection-oriented protocol
    Uses 3-way handshake to establish communication

  * User Datagram Protocol (UDP)
    Connectionless protocol with less overhead
    Windowing and buffering of frames

### Layer 3: Network Layer
Primary function is to forward packets from end to end
Concerned with logical addressing of host using IP addresses. Makes routing decision and forward data
between networks. Operates on the unit of datagrams. Devices include routers and layer 3 switches.

* Routing is the process forwarding datagrams between sub networks (subnets) using a router.
  Router operations are implemented in software.

* Subnet is a network segment at the network layer level. Subnetting of diving network into smaller
  sections (subnets). Each network has one subnet by default. Each subnet has a:
  - Netmask
  - IP range
  - Subnet Mask

* Internet Protocol (IP) is a routable protocol that uses IP address to deliver packets to network
  devices.

  IP Address is a unique number used to identify a host in a network. Each IP has two sections.
  Network section used to identify the subnet and the host section used to identify the host in the
  subnet.

  IP Versions
  - IPv4: A 32 bit number divided into 4 octets. Each octet ranges from 0 to 255. Eg: 192.168.10.13
  - IPv6: A 128 bit number used to identify a host. It has larger address space than IPv4.

* Datagram is the basic unit of transmission at the network layer (also called packet).
  Datagrams are connectionless messages sent in one direction without requiring acknowledgement.

  Types of Datagrams:
  - Unicast: From one device to another device. Destined to one host.
  - Broadcast: From one device to all devices within the same network segment (subnet).
  - Multicast: Message from one device to a set of device that listen for them.
    Devices join multicast group to receive multicast datagrams.

### Layer 2: Data Link Layer
Primarily implemented in software and maybe embedded in physical devices (Firmware) such as switches
and network adaptors. Responsible for transferring data between devices on the same network segment.

Groups of bits are transmitted in unit of frames.
Divided into 2 sublayers: MAC sublayer and Logical Link Control.

* Media Access Control (MAC) Sublayer:
  Concerned with physical addressing of the device.
  MAC address is a 48-bit address unique to the Network Interface Card (NIC).
  Defines the logical topology (Ethernet, Token ring etc)
  And method of data transmission (CSMA/CD, CSMA/CA)
  Detects or Avoids frame collisions.
  Determines the start and end of a frame.

* Logical Link Control (LLC) Sublayer
  Provides the connection service
  Clock synchronization for transmission
  Isochronous, Synchronous and Asynchronous
  Multiplexing, Flow control and error notification using CRC in frames received.

Devices include layer 2 switches or layer 3 switches, NICs and Bridges.

Frames
A frame consists of layer 2 header, payload, and Frame Sequence Checksum for error checking.
Size of a frame: Header is about 22-26 bytes, Payload is 1500 bytes and FCS is 4 bytes.

+=================================+
| Header  | Payload   | FCS (CRC) |
+=================================+

802.3 Ethernet Header
+==========+=====+=======+=======+==========+======+=====+=====+
| Preamble | SFD | D MAC | S MAC | VLAN Tag | Size | ... | FCS |
+==========+=====+=======+=======+==========+======+=====+=====+

- Preamble:
- Start of Frame Delimeter (SFD):
- Destination MAC Address:
- Source MAC Address:
- Virtual LAN (VLAN) Tag:
- Size:
- Frame Check Sequence (FCS) or Cyclical Redundancy Check (CRC):

Frame headers & Checksums add overheads to the payload to be transmitted.
Collision is when devices in the same network segment try to send data at the same time over a shared
medium and it's responsible for sensing when a channel is in use (CSMA).
Detect and Avoid collision (CD/CA).

### Layer 1: Physical Layer
Primarily consists of hardware that provides basic communication channel for transmission and
reception of bits/signals. Different physical layer links exists for different purposes;
Including multiple varieties of wired electric cables, wireless radio and optical connection.

- Synchronization
- Bandwidth usage
  Broadband: Multiple conversations use different frequency ranges.
  Baseband: Entire conversation is done in a single frequency.
- Physical network topology (Bus, Ring, Star etc).
- Isolate electrical/optical circuits
- Bit Encoding:
  Bits are encoded into analog signals for transmission and decoded at reception.
  Uses the absence or presence of voltage to encode/decode bit into physical signal.
  Transmit bits over physical link.

  Types of analog signal:
  Electrical pulses over twisted pairs
  Radio signals through the air
  Pulses of light through fiber optic cable

  * Specifications:
  Type of connection i.e. Electrical/Optical/Radio
  Physical requirements for connectors/anthenas and other attachment needed for the network to function.
  Defines the communication hardware needed to implement the network.

  Cable/Wired Examples:
  Ethernet Physical layer, DSL Physical layer, Cable modem, Dial-up modem (V.92 Standard)

  Wireless Examples:
  Wifi Physical (IEEE 802.11), Bluetooth physical, GSM Um interface, LTE physical interface

  Optical Examples:
  Fiber optic (SONET) physical layer, IRDA Physical layer (Wireless infrared).

## TCP/IP Model
Transmission Control Protocol/Internet Protocol is the current networking architecture in practice.
It is a 4/5 layer Model. It combines layer 5,6 and 7 of the OSI reference model into one as application layer.
Provides framework for transmitting data and requires basic information to transmit the data in a network.

TCP/IP Layer Stack:
* Application Layer (Applications that communicates remotely. Eg: Web Browsers, email clients etc.
  Protocols: http/s, ftp etc. PDU: message)
* Transport Layer (Establish connection between remote host. Protocols: TCP/UDP. PDU: segment/datagram.
  Ensures that data gets to the right application)
* Network Layer (Allows different networks to communicate using routers. protocol: IP. PDU: packet)
* Data Link Layer (Creates frames, uses MAC address locate host in LAN. protocols: Ethernet, Wi-fi etc)
* Physical Layer (The Physical devices and Transmits bits between devices.)

### Layer 1: The Physical Layer
* Moving Bits across the wire: consist of devices that transmits bit across the network devices.
  Bit is the smallest representation of data a computer can understand and transferred using modulation.
  Modulation is the way of varying the voltage of discharge across the cable known as Line Coding.

* Twisted Pair Cable: Most type of cable to connect network and allows for duplex communication.
  Duplex communication is a way of communicating in both direction
    Full duplex allows communication in both direction at the same time.
    Half duplex allows one communication at a time.
    Simplex opposite of Duplex where communication is in one direction only.

* Network Ports and Patche Panel
  Most common network port is RJ45 
  Patch panel device contain many ports

### Layer 2: The Data Link Layer
* Ethernet and MAC addresses
  Ethernet is most common protocol for sending data and it operates at the data link layer.
  It abstracts the network device used in the physical topology.

  MAC addresses is 48-bit hexadecimal number used to identify a network interface represent by six
  groupings of two hex numbers.

* Unicast, Multicast and Broadcast
  Unicast is transmission meant for one address
  Multicast is sent to all device in a network and get discarded 
  Broadcast

* Ethernet frame
 - Preamble - 8 bytes, alternating 1s and 0s, SFD preamble is over.
 - Destination MAC 48 bits
 - Source MAC
 - EtherType field
 - VLAN header
 - Payload - Actually data being transport
 - FCS - 4-byte checksum calculated using CRC 

### Layer 3: Network Layer (Internet Layer)

### Layer 4: Transport Layer

### Layer 5: Application Layer

