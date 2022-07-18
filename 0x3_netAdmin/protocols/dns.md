# INTRODUCTION - DOMAIN NAME SYSTEM (DNS)
-----------------------------------------
DNS:
Developed by Paul Mockapetris in 1983

It's a Hierarchical and Decentralized Naming system used to identify
computers, services or resources on the internet or on Private Networks.

DNS is part of TCP/IP suite that function at the application layer and uses UDP port 53
DNS is a distributed and dynamic way of resolving FQDNs to IP addresses, Translates Hostname to IP address (names-to-IP address).

Delegates Domain names and assigns IP addresses to names. DNS Servers store and resolve hostnames to IP addresses requested by a client.
It uses its underlying protocol to locate and identify computer devices and services on a the internet.

Phonebook of the internet.

## Domain Name (DN)
-------------------
Unique set of characters use to identify specific network domain / represent an IP resources in a network. It is organized in a subordinate level known as subdomains.

Domain names are arranged in a hierachical form: from top level to subdomains. A domain name must be registered with ICANN usually through the DN registrars.

DNS root - nameless (.)
Top Level Domains (TLDs) - gTLD, ccTLD (.com, .org .co.uk, .gh, .in etc)
  
Second&Third Level Domains - open for reservation by end users to lookup host on the internet using DNS.

Fully Qualified Domain Name (FQDN) - A domain with all labels specified and might include DNS root.

## HOW DNS WORK
----------------
Client request for data. The cache is first searched and if not found, queries the root nameserver 

- Recursive Resolver
 Receives queries from clients
 makes additional queries to resolve clients request
 
- Root nameserver (Root Server)
 First stop in dns lookup process. Redirects query to more specific TLD nameserver if not found in cache.
 Root servers operate in the root zone zone of the DNS hierarchy.
 
- TLD nameserver
 Next stop in search for an IP address of a domain. It host the last portion of the hostname
 
- Authoritative nameserver
 The last stop in query. Returns the IP address hostname to the client if it has access to it in the record via the recursor.

Data is return to client and cached or returns an error when times out or not found

## DNS COMPONENTS
------------------
- Cache
- Resolvers
- Nameservers
- Namespace

## DNS ZONE FILES
------------------
Instructions that Lives in the authoritative dns nameserver.
Contains information of the domain, how requests of that domain is handled.

==================================================================================================================
