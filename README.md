# A simple User Datagram Protocol (UDP) implementation
Blaster Blastee

* created by Clarence Cheung, Jin Ruan
* Fall 2015
* Copyright (c) 2015 Clarence Cheung, Jin Ruan

Description:
The blaster sends UDP packets to specified host
The blastee receives UDP packets from the blaster 
- blaster.c / client
- blastee.c / server

UDP packets are in the following format:
| 8 bit packet type | 32 bit sequence | 32 bit length | payload |

The following are valid values for packet type in this application:
- 'D': DATA packet
- 'E': END packet
- 'C': ECHO packet

blaster and blastee are invoked as such:
* blaster -s [hostname] -p [portnum] -r [rate] -n [numpkts] -q [seqnum] -l [length] -c [echo]
* blastee -p [portnum] -c [echo]
 
Note:
- hostname: Hostname
- portnum: Port number
- rate: Number of packets to be sent per second
- numpkts: Number of packets to be sent by the blaster
- seqnum: Sequence number
- length: Length of the variable payload in bytes from the packets
- echo: Parameter that tells the blaster if expecting echo of packets from blastee. 1= echo, 0= no echo.

Additional note:
- valid port number: 1024 < portnum < 65536 
- length: Payload length < 50 KB

