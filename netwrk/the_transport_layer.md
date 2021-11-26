--[ TRANSPORT LAYER
Transport Layer allows traffic to be directed to specific network applications.
* Multiplexing & Demultiplexing
* Ports & Sockets

** Dissecting TCP Segment

* TCP Control Flags & Three-way Handshake

* TCP Control Flags
- URG (urgent)
- ACK (Acknowledge)
- PSH (Push)
- RST (Reset)
- SYNC (Synchronise)
- FIN (Finish)

* Establishing TCP connection (3-way Handshake)
SYNC --->
<--- SYNC/ACK
----> ACK

* Closing TCP Connection (4-way Handshake)
FIN ---> 
ACK <---
FIN <---
ACK --->

* Socket States
- LISTEN
- SYN_SENT
- SYN-RECIEVED
- ESTABLISHED
- FIN_WAIT
- CLOSE_WAIT
- CLOSED

** Dissecting UDP datagram
* Difference between TCP & UDP
** Firewall