--[ The Network Layer
 The network layer (layer 3) transport and deliver data across different networks that may or may not be connected directly.
 Protocol Data Unit at the network layer is called an IP Datagram
 The router which operates at the network layer makes a forwarding decision  after inspecting the IP datagram header.
 The network layer is able to fragment frames at the source or intermediate system and formats them at the destination.
 
 * IP Adresses (Verion 4 | IPv4)
  - A 32-bit number grouped as 4 octet using dotted decimal notation.
  - Assigned to a host connected to a network that uses IP protocol.
  - used to identify a host in a network
  - IP addresses belong to a network
  - Addresses are assigned either static or dynamic
  - Range of a valid IP address: 0-255 in each octet
  - Each octet is 8-bit or 1 byte
  - IP addresses has 2 sections: network ID and host ID
  - Network ID is used to identify the subnet
  - Host ID is used to identify the host in the subnet.

 * IP Datagrams and Encapsulation
  |- Highly structured series of fields that are strictly defined
  |- Has 2 primary parts: Header and Payload
  |- Fields in the IP Datagram Header:
   - version: the most common is version 4 (IPv4) and 4-bit in size.
   - Header Length Field: Length of the IP header. Min: 20B and Max: 60B.
   - Service Type field: Specify QoS.
   - Total Length: total size of the datagram; header length + payload.
   - Identification: used to group messages of the same packet.
   - Flags Field: 0-bit, DF-bit and MF-bit
   - Fragmentation offset: position of a fragmented datagram in the main. [^1]
   - Time To Live (TTL Field): Router hops count.
   - Protocol: transport layer protocol in used
   - Header Checksum: 
   - Source IP:
   - Destination IP:
   - Options: 
   - Padding:
  |- Encapsulation: upper layer used as payload to lower layers

 * IP Address Classes
  |- Class A: Leading Bit is always zero (0)
  |- Class B: First bit is one (1) and Second bit is zero (0)
  |- Class C: First two bits are one and the third bit is zero (0).
  |- Class D: Reserved for Multicasting, Range: 224-239
  |- Class E: Reserved for Research and Testing, Range 240-255

 * Address Resolution Protocol (ARP)
 - used to discover MAC address associated with a given IP address in subnet.
 - Request-Response protocol
 - Communicates within the boundaries of a single subnet.
 - Lies between IP layer and the Link layer

--[ Subnetting
 - The process of dividing network into smaller is sections.
 - Easier to isolate group of host for easier troubleshooting/maintainance.
 - Netmask is used to distinguish different subnets.
 - Some of the host bit are borrowed in other to create additional subnet.
 - Netmask
 - IP address
 - Host bit with all 0s are usually unused
 - Host bit with all 1s are for broadcast.
 - 2^n-2 = # host in a subnet, n = # of bit for host
 - Eg: IP = 192.168.0.15, netmask = 255.255.255.0
 - Borrowed Host bit = 1, Total subnet = 2, # host in subnet = 2^7-2
 - 1. subnet ID = 192.168.0.0, Subnet Broadcast = 192.168.0.127
 - Host range = 192.168.0.1-126
 - 2. subnet ID = 192.168.0.128, subnet Broadcast = 192.168.0.255
 - Host range = 192.168.0.129-254
> The opposite of subnetting is Supernetting; to create a larger network

--[ Routing, Routing Table, Routing Protocols & Non-Routable IP Addresses
* Routing 
- The process of sending traffic from source to destination using the best
   path 
 - Router is a device that forwards traffic from sources to destination
   depending the destination address
 - Forwarded traffic may hop through different intermediate systems before
   reaching it destination.

* Routing Table
  Routers keep a list of destination networks for apropriate routing of traffic. Also known as Routing Information Base (RIM)

* Routing Protocols
  Special protocols routers use to communicate, share routing paths
  2 Categories: Interior & Exterior Gateway Routing Protocols
  Interior Gateway Routing Protocols: used by routers to share information
  within a single autonomous system.
 - Autonomous Systems (AS): Collection of networks under control of a single
   operator.
  2 Types of Interior Gateway protocol: Link State routing Protocol &
  Distance-vector protocols.
  Exterior Gateway Protocols: Share information with different AS using BGP

* Non Routable IP Addresses
According to standards set forth in IETF document (RFC 1918), the following address ranges are reserved for IANA for private internets and are not publicly routable on the global internet.

- 10.0.0.0/8
- 172.16.0.0/12
- 192.168.0.0/16

> Interior Gateway Routing Protocols may route private addresses within an AS but Exterior Gateway Routing Protocols (BGP) will reject private addresses.

--[ Glossary
PDU: Protocol Data Unit
SDU: Service Data Unit
IP Packet:
Encapsulation: PDU from upper layer being wrapped in the lower layer
IP Fragmentation: Breaking IP packet into smaller pieces 
AS: Automous System
ASN: Autonomous System Number
BGP: Border Gateway Protocols