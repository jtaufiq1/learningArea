-[ Beneath the Internet

# TCP/IP Model 
---------------

Develop by the Department of Defense (DoD) and 
Defense Advanced Research Project Agency (DARPA).

Open Standard that can be used to connect computers 
together and exchange information.

The basis of the internet.

# Layers
---------
* Application Layer
* Transport Layer
* Internet (inter-network) layer
* Network Layer

# Application Layer
-------------------
It creates the payload that all the other layers carry.
Basically the application that are used to communicate/
exchange information over a network.

Eg: Web Browsers (Firefox, chrome etc), email clients etc.

The application layer creates the package, wraps it with 
instructions on how the package should be used. It then 
hands it over to the transport layer.

# Transport Layer
------------------
The transport layer setup network connections (sessions).
The protocols at the transport layer are TCP and UDP.

* TCP
Transmission Control Protocol 
Adds wrapping to the outside of the package with instructions about it,
How to make sure the package got to the destination and whether the
package is intact.

The package is broken up into segments before it being transmitted. It is
then reassembled upon its arrival at the destination in the correct order.

* UDP
User Datagram Protocol
Transmits streams of datagram similar to segments but acknowledgement or
errors are not checked or whether the datagrams are received or not.

* Port
TCP and UDP traffic is assigned to specific port numbers at this layer.

# Internet (Internetwork) Layer
--------------------------------
The information of source and destination addresses is added at this layer,
and where the packets begins and ends.
The protocol at this layer is the IP (Internet Protocol). It uses the
IP addresses to get packets to the right place using the best route.

# Network Access
-----------------
The low-level physical network that is used to connect the internet.
This layer consists of network cables, Network Interface Card (NIC) or
wireless card and access point. It handles the lowest level of ones and
zeroes (bit).

# Protocols
------------
It simply the rules that tells how a layer operates in a network.

* Application Layer Protocols
- FTP: File Transfer Protocol. Uses one port to deliver data and
another port to send control signals. common port: 20 and 21 (TCP).

- HTTP: Hyper-Text Transfer Protocol is used for web pages. TCP port
80. HTTPS - secure variant uses port 443.

- SMTP: Simple Mail Transfer Protocol is used to send emails and
uses port 25.

- DNS: Domain Name Service is how domain name is mapped to an IP address.
It uses port 53 (UDP).

* Transport Layer Protocols
- TCP: Establishes a logical connection (a session) between two hosts in 
a network using 3 way handshake.

1. Host A sends SYN packet to host B. ie, synchronize clocks, exchange traffic
with timestamps.

2. Host B responds with SYN/ACK acknowledgement packet.

3. Host A seals the deal with ACK packet and session is established.

- UDP: User Datagram Protocol. Connectionless protocol. broadcast streams of datagram.
very fast connection.

* Internet layer protocols
- IP: Internet Protocol. Allows 2 hosts to communicate through network. Delivers packet at
the destination address.

* Internet Control Message Protocol (ICMP)
- ICMP: used to troubleshoot and maintain a network. Includes commands that can be used to 
test and report errors
