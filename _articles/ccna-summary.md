---
published: true
subtitle:
topic: CCNA
date: 2022-09-01
tags: CCNA Networking Study
---

# CCNA

## Preface
This is by no means an exhaustive study guide for the topics on the CCNA, but rather a review tool that briefly touches on each topic outlined in the CCNA 200-301 Exam Description.


## 1.0 Network Fundamentals
A computer network is a digital telecommunications network which allows nodes to share resources. In computer networks, computing devices exchange data with each other using connections (data links) between nodes. These data links are established over cable media such as wires or optic cables, or wireless media such as Wi-Fi.
## 1.1 Explain the role and function of network components

###     1.1.a Routers
Routers provided connectivity between LANs (Local Area Networks), and are therefore used to send data over the Internet.  
###     1.1.b Layer and Layer 3 switches
Switches provide connectivity to hosts within the same LAN. Switches typically have many more network interfaces/ports for end hosts to connect to (usually 24+).
Layer 3 switches 
###     1.1.c Next-generation firewalls and IPS
Firewalls monitor and control network traffic based on configured rules. They are known as "Next-Generation Firewalls" when they include more modern and advanced filtering capabilities.
Network firewalls are hardware devices that filter traffic between networks. 
Host-based firewalls are software applications that filter traffic entering and exiting a host machine, like a PC.
###     1.1.d Access points

### 1.1.e Controllers (Cisco DNA Center and WLC)

### 1.1.f Endpoints/End hosts
An endpoint is a remote computing device that communicates back and forth with a network, examples include computers, laptops, mobile phones, tablets, and servers.
### 1.1.g Servers
A server is a device that provides functions or services for clients/endpoints on a network.
### 1.1.h PoE
Power over Ethernet


## 1.2 Describe characteristics of network topology architectures

### 1.2.a Two-tier

### 1.2.b Three-tier

### 1.2.c Spine-leaf

### 1.2.d WAN

### 1.2.e Small office/home office (SOHO)

### 1.2.f On-premise and cloud


## 1.3 Compare physical interface and cabling types
RJ-45 (RJ = Registered Jack) - Standard connector for copper UTP cables that has 8 pin connections.

UTP cables - Unshielded twister pair copper wire, contains 4 pairs of wires twisted together, with 8 wires in total.

Straight-through cable - 

Crossover cable - 

Using Auto MDI-X, devices are able to automatically detect which pins their neighbor is using to transmit data and automatically adjust their pins to receive and transmit on the correct pins.
### 1.3.a Single-mode fiber, multimode fiber, copper
SFP Transceiver (SFP = Small Form-Factor Pluggable) - connector used for fiber-optic ports on a switch, connects to Fiber-Optic cabling.
Single-mode fiber is narrower than multimode fiber, light enters at a single angle (mode) from a laser-based transmitter. Allows for longer cables than both UTP and multimode fiber, but also more expensive.
Multimode fiber is wider than single-mode fiber, allows multiple angles (modes) of light waves to enter the fiberglass core. Allows longer cables than UTP, but shorter than single-mode fiber.
### 1.3.b Connections (Ethernet shared media and point-to-point)


## 1.4 Identify interface and cable issues (collisions, errors, mismatch duplex, and/or speed)
Day 9 video
## 1.5 Compare TCP to UDP

## 1.6 Configure and verify IPv4 addressing and subnetting
pictures
CIDR (Classless Inter-Domain Routing) removed the previous requirements of:
    Class A = /8
    Class B = /16
    Class C = /24
This allows larger networks to be split into smaller networks, allowing greater efficiency.
These smaller networks are called "subnetworks" or "subnets".

Using VLSM (Variable-Length Subnet Masks) will allow the creation of subnets of different sizes, to make use of network addresses even more efficient.
## 1.7 Describe the need for private IPv4 addressing

## 1.8 Configure and verify IPv6 addressing and prefix


## 1.9 Describe IPv6 address types

### 1.9.a Unicast (global, unique local, and link local)

### 1.9.b Anycast

### 1.9.c Multicast

### 1.9.d Modified EUI 64

## 1.10 Verify IP parameters for Client OS (Windows, Mac OS, Linux)


## 1.11 Describe wireless principles

### 1.11.a Nonoverlapping Wi-Fi channels

### 1.11.b SSID

### 1.11.c RF

### 1.11.d Encryption


## 1.12 Explain virtualization fundamenetals (server virtualization, containers, and VRFs)


## 1.13 Describe switching concepts
MAC Address is a 6-byte (48-bit) globally unique physical address assigned to the device when it is made. Written as 12 hexadecimal characters. (00:00:00:00:00:00)
### 1.13.a MAC learning and aging
When a switch receives a frame, it associates the MAC address of source with the corresponding port which the frame was received. The switch dynamically constructrs an address table using the MAC source addresses of received frames.
These dynamically learned MAC addresses are deleted from the table after the MAC address age value has expired. This frees unused addresses from the MAC address table for other active subscribers. The default value is 300 seconds.


Static MAC addresses can be assigned to the table, which are retained during a switch resest.

### 1.13.b Frame switching

### 1.13.c Frame flooding
When the switch receives a frame for a destination MAC address that is not in its address table, it floods the frame out of all LAN ports of the same VLAN except for the port that the frame received.
When the destination station responds, the switch adds its relevant MAC source address and port ID to the address table.
### 1.13.d MAC address table
To exchange frames between LAN ports efficiently, the switch maintains a MAC address table. The switch learns and builds it's adress table through the processes described above, and is able to forward the subsequent frames to a single port without flooding all the LAN ports.


## 2.0 Network Access

## 2.1 Configure and verify VLANs (normal range) spanning multiple switches
VLANs are configured on switches on a per-interface basis, and logically seperate end hosts at Layer 2. Switches do not forward traffic directly between hosts in different VLANs, it must forward the traffic to a router to perform inter-VLAN routing.

show vlan brief
### 2.1.a Access ports (data and voice)
An access port is a switchport which belongs to a single VLAN, and usually connects to end hosts like PCs

### 2.1.b Default VLAN
VLAN 1 is the default VLAN.
VLANs 1002-1005 exist by default and cannot be deleted.
### 2.1.c Connectivity


## 2.2 Configure and verify interswitch connectivity

### 2.2.a Trunk ports
Trunk ports are switchports which carry multiple VLANs. 
### 2.2.b 802.1q

### 2.2.c Native VLAN

## 2.3 Configure and verify Layer 2 discovery protocols (Cisco Discovery Protocol and LLDP)

## 2.4 Configure and verify (Layer 2/Layer 3) EtherChannel (LACP)

## 2.5 Interpret basic operations of Rapid PVST+ Spanning Tree Protocol

### 2.5.a Root port, root bridge (primary/secondary), and other port names

### 2.5.b Port states (forwarding/blocking)

### 2.5.c PortFast

## 2.6 Describe Cisco Wireless Architectures and AP modes

## 2.7 Describe physical infrastructure connections of WLAN components (AP, WLC, access/trunk ports, and LAG)

## 2.8 Describe AP and WLC management access connections (Telnet, SSH, HTTP, HTTPS, console, and TACACS+/RADIUS)

## 2.9 Interpret the wireless LAN GUI configuration for client connectivity, such as WLAN creation, security settings, QoS profiles, and advanced settings

## 3.0 IP Connectivity

## 3.1 Interpret the components of routing table

### 3.1.a Routing protocol code
### 3.1.b Prefix
### 3.1.c Network mask
### 3.1.d Next Hop
### 3.1.e Administrative distance
### 3.1.f Metric
### 3.1.g Gateway of last resort

## 3.2 Determine how a router makes a forwarding decision by default

Routers drop packets with unknown destinations.

### 3.2.a Longest prefix match
When a router looks up a destination address in its routing table, it looks for the most specific matching route. Most specific = longest prefix length ( /32 > /24 > /16 > /8 > /0)
### 3.2.b Administrative distance
### 3.2.c Routing protocol metric

## 3.3 Configure and verify IPv4 and IPv6 static routing
to configure: 
ip route (destination ip address) (mask) (next-hop ip address)
ip route (destination-address) (mask) (exit-interface)
to verify: 
show ip route

### 3.3.a Default route
### 3.3.b Network route
### 3.3.c Host route
### 3.3.d Floating static

## 3.4 Configure and verify single area OSPFv2
### 3.4.a Neighbor adjacencies
### 3.4.b Point-to-point
### 3.4.c Broadcast (DR/BDR selection)
### 3.4.d Router ID

## 3.5 Describe the purpose, functions, and concepts of first hop redundancy protocols

## 4.0 IP Services
## 4.1 Configure and verify inside source NAT using static and pools
## 4.2 Configure and verify NTP operating in a client and server mode
## 4.3 Explain the role of DHCP and DNS within the network
## 4.4 Explain the function of SNMP in network operations
## 4.5 Describe the use of syslog features including facilities and levels
## 4.6 Configure and verify DHCP client and relay
## 4.7 Explain the forwarding per-hop behavior (PHB) for QoS, such as classification, marking, queuing, congestion, policing, and shaping 
## 4.8 Configure network devices for remote access using SSH
## 4.9 Describe the capabilities and function of TFTP/FTP in the network

## 5.0 Security Fundamentals
## 5.1 Define key security concepts (threats, vulnerabilities, exploits, and mitigation techniques)
## 5.2 Describe security program elements (user awareness, training, and physical access control)
## 5.3 Configure and verify device access control using local passwords
## 5.4 Describe security password policies elements, such as management,complexity, and password alternatives (multifactor authentication, certificates, and biometrics)
## 5.5 Describe IPsec remote access and site-to-site VPNs
## 5.6 Configure and verify access control lists
## 5.7 Configure and verify Layer 2 security features (DHCP snooping, dynamic ARP inspection, and port security)
## 5.8 Compare authentication, authorization, and accounting concepts
## 5.9 Describe wireless security protocols (WPA, WPA2, and WPA3)
## 5.10 Configure and verify WLAN within the GUI using WPA2 PSK

## 6.0 Automation and Programmability
## 6.1 Explain how automation impacts network management
## 6.2 Compare traditional networks with controller-based networking
## 6.3 Describe controller-based, software defined architecture (overlay, underlay, and fabric)
### 6.3.a Seperation of control plane and data plane
### 6.3.b Northbound and Southbound APIs

## 6.4 Compare traditional campus device management with Cisco DNA Center enabled device management
## 6.5 Describe characteristics of REST-based APIs (CRUD, HTTP verbs, and data encoding)
## 6.6 Recognize the capabilities of configuration management mechanisms Puppet, Chef, and Ansible
## 6.7 Recognize components of JSON-encoded data

