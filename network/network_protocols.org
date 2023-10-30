#+title:network protocols
#+filetags: :network:protocol:protocols:TCP:UDP


* TCP                                                                   :tcp:
is a realiable, more slow protocol that focus on delivering data safely
the TCP header has 20 bytes

features:
+ 3 way handshake: makes stable connection between hosts
+ acknowledgement: confirms connection
+ checksum: detects corrupted data
+ sequence: detects missing data and rebuild it in the correct order
+ retransmission: retransmits missing or corrupted data'

** 3 way handshake
stabilishes a stable connection before data transfer

the flags used are:
HOST: SYN
PC: SYN+ACK
HOST: ACK


* UDP                                                                   :udp:
focus on delivering data fast
the UDP header has 8 bytes


* ARP and RARP (subprotocol)                                       :arp:rarp:
resolves an IP into a MAC address, resolves MAC into an IP (R(everse)ARP)

if the host wants to know an MAC address via IP,
arp sends a broadcast message to all LAN devices

if the host wants to know an IP adderss via MAC,
rarp sends a broadcast message to all LAN devices


* ICMP                                                                 :icmp:
generates error responses to the origin IP when network issue
prevents a package deliver, but doesnt solve it

** types of messages
+ echo request/echo reply: checks connectivity, a host asks for echo, another replies
+ distination unreachable: sent by a router when it cant deliver an IP package
+ redirect: sent by a router if it receives a package that should be sent to another router.
  It contains the IP which future package must be delovered to, useful to fasten redirect
+ time exceded: sent by a router if package exceed the routers it was permited to reach (TTL)
