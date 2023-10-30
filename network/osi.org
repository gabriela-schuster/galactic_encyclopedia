#+title:OSI
#+filetags: :network:osi:

* structure (layers)                                              :structure:
[[../images/osi.png]]
host layers are within the computer, the media layers not


* application layer                                             :application:layer:
interface between an app/protocol and the user
+ SMTP
+ HTTPS


* presentation layer                                             :presentation:layer:
certifies data in the application layer can be understood by another application
+ HTML converted to ASCII
+ cryptography
+ translates formats (images, video, XML, JavaScript)


* session layer                                             :session:layer:
configures, manages and ends "apps sessions" between devices in the network,
grants data is correctly redirected to the correct app receiving/sending it
** communication methods
+ simplex: one device talks, the others listen (ex. radio)
+ half duplex: everyone can talk, but one at each time (ex. walkie-talkie)
+ full duplex: everyone can talk at the same time (ex. telephone call)


* transport layer                                             :transport:layer:
transfers data without errors,
disassemble and reassemble data so it can be delivered in packages
+ UDP
+ TCP


* network layer                                             :network:layer:
 routing and IP addressing,
 modifies packages so it has the origin IP and destination IP
 + IPv4
 + IPv6


* data link layer :data_link:layer:
transfers frames to the correct LAN device, using MAC and LLC
** LLC (logical link control)
+ controls errors and flux control
+ corrects corrupted frames
+ limits data quantity to avoid overload
** MAC (media access control)
+ phisical addressing of 48 bits stored in NIC

* physical link                                              :physical:layer:
transfers frames to the correct LAN device, using MAC and LLC
** LLC (logical link control)
+ controls errors and flux control
+ corrects corrupted frames
+ limits data quantity to avoid overload
** MAC (media access control)
+ phisical addressing of 48 bits stored in NIC


transfers bits, hardware itself
+ hubs, modems
