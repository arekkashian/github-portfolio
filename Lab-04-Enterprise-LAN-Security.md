# Lab 04: Enterprise LAN Design and Security Assessment
Arek Kashian  
IT 520  
April 3, 2026


## Part 1

The first layer of the OSI model is the physical layer, which in this setup is entirely copper ethernet cabling. This is how information is conveyed between devices on the network as electrical signals

### MAC Addresses

IT Operations Router 1

- Workstation 1: 0060.47EE.6C48
- Workstation 2: 0001.C9A4.CC55
- Workstation 3: 0090.216A.4550


Operational Technology Router 2

- Web Server: 000D.BD91.E987
- SCADA Device 1: 0040.0B3B.3A0A
- SCADA Device 2: 0004.9A55.259C

Remote Pump Station Router 3

- Pump Controller: 0090.2116.EE5A
- Attacker Node: 0001.63BD.BEB4

![Logical map](packettracermap.png)

![Physical map](physicalmap.png)

## Part 1.2 - MAC Addresses and Switching

This is the second layer of the OSI model, the data link layer. The switch sorts packets according to what physical device they are supposed to go to, identified by the MAC, and which is linked to an IP address automatically by the switch as traffic crosses through it

![MAC table](switchtable.png)


## Part 1.3 Network Layer Configuration (Routing)

Routing represents level 3 of the OSI model, the network layer, as it represents in a logical way the connections between different devices, allowing for data to flow between them with actual directions as opposed to a mass broadcast, and IP addresses also enable this function

![Routing table](router.png)

## Part 1.4 Connectivity Verification

![Pinging endpoints](ping.png)

# Part 2

The TCP handshake system allows for better security because it requires both parties in the communication to identify themselves and form a steady connection, without which the packets do not make it to the application layer

TCP and UDP operate at level 4 of OSI, the transport layer, because they are encapsulations of data to transport them across the logical network formed by the router and IP address system.

## Part 2.2

TLS and HTTPS prevent man in the middle attacks by encrypting the data sent over SSH with a key exchange between the browser and the server beforehand. This encryption is operating at the presentation or the session layer according to different sources, the session layer seems more accurate to me

![HTTP and HTTPS service](webs.png)

![Remote control of router](router2.png)


SSH replaced telnet because requiring encryption keys adds an additional layer of security and makes it harder to brute force passwords, and telnet is transmitted in plaintext making man in the middle attacks very easy



# Conclusion

This assignment showed to me that network design and architecture cannot really be separated from security and they are largely the same thing. There are exceptions like shellshock that target vulnerabilities in particular versions of system software but the basic architecture will greatly expand or reduce the attack surface. Configuring a network at this level of granularity is not something I had experience with before and has been very interesting.
