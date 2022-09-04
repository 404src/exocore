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
###     1.1.b Layer 2 and Layer 3 switches
Switches provide connectivity to hosts within the same LAN. Switches typically have many more network interfaces/ports for end hosts to connect to (usually 24+).
Layer 3 switches, also known as Multilayer switches, are capable of both switching AND routing.
Layer 3 switches can have IP addresses assigned to its interfaces, like a router. 
You can also create virtual interfaces, or SVIs (switch virtual interfaces), for each VLAN, and assign IP addresses to those interfaces.
These SVIs are used as the gateway address for each PC, instead of a router.
To send traffic to different subnets/VLANs, the PCs will send traffic to the switch, and the switch will route the traffic. 
Routes can be configured on Layer 3 switches, and it can be used for inter-VLAN routing.
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
Trunk ports = "tagged" ports
Access ports = "untagged" ports

DTP (Dynamic Trunking Protocol)
    -Cisco proprietary protocol that allows Cisco switches to dyniamically determine their interface status (access or trunk) without manual configuration. For security purposes, manual configuration is reconmmended and DTP should be disabled on all switchports.
VTP (VLAN Trunking Protocol)
    -allows you to configure VLANs on a central VTP server switch, and other switches (VTP clients) will synchronize their VLAN database to the server. It is designed for large networks with many VLANs, but is rarely used and not recommended.
### 2.2.a Trunk ports
Trunk ports can be used to carry from multiple VLANs over a single interface. Switches will "tag" all frames that they send over a trunk link. This allows the reciving switch to know which VLAN the frame belongs to.

show interfaces trunk
### 2.2.b 802.1q
802.1q is an industry standard trunking protocol.

The 802.1q tag is inserted between the Source and Type/Length fields of the Ethernet frame.
The tag is 4 bytes (32 bits) in length and consists of two main fields: TPID (Tag Protocol Identifier) and TCI (Tag Control Information).
The TPID is 2 bytes in length and is always set to a value of 0x8100, indicating the frame is 802.1q tagged
The TCI consists of 3 smaller fields:
    -PCP (Priority Code Point), 3 bits
        -used for CoS (Class of Service), which prioritizes important traffic in congested networks.
    -DEI (Drop Eligiblle Indicator), 1 bit
        -used to indicated frames that can be dropped if the network is congested 
    -VID (VLAD ID), 12 bits
        -identifies the VLAN the frame belongs to. 
### 2.2.c Native VLAN
802.1q has a feature called the native VLAN.
The native VLAN is VLAN 1 by default on all trunk ports, but can be manually configured on each trunk port.
The switch does not add an 802.1q tag to frames in the native VLAN.
When a switch receives an untagged frame on a trunk port, it assumed the frame belongs to the native VLAN. For this reason, it's very important that the native VLAN matches for both switches.

R1(config-subif)#encapsulation dot1q (vlan-id) native
## 2.3 Configure and verify Layer 2 discovery protocols (Cisco Discovery Protocol and LLDP)

## 2.4 Configure and verify (Layer 2/Layer 3) EtherChannel (LACP)
When the bandwidth of the interfaces connected to end hosts is greater than the bandwidth of the connection to the distribution switch(es), this is called oversubscription, which can cause congestion.
EtherChannel groups multiple interfaces together to act as a single interface. STP will treat this group as a single interface.
EtherChannel is also known as Port Channel, or LAG (Link Aggregation Group)
EtherChannel load balances based on "flows". A flow is a communication between two nodes in the network. Frames in the same flow will be forwarded using the same physical interface.
The inputs used in the interface selection calculation can be configured
    -inputs that can be used:
        1. Source MAC
        2. Destination MAC
        3. Source AND Destination MAC
        4. Source IP
        5. Destination IP
        6. Source and Destination IP

((----------picutre--------))


There are three methods of EtherChannel configuration on Cisco switches:
    1. LACP (Link Aggregation Control Protocol), 802.3ad 
        - Dynamically negoties the creation/maintenance of the the EtherChannel (similary to DTP for trunks)
    2. PAgP (Port Aggregation Protocol)
        - Cisco propretary protocol
        - Dynamically negotiates the creation/maintenance of the EtherChannel.
    3. Static EtherChannel
        - A protocol isn't used to determine if an EtherChannel should be formed. 
        - Interfaces are statically configured to form an EtherChannel.
Up to 8 interfaces can be formed into a single EtherChannel (LACP allows up to 16, but only 8 will be active, the other 8 will be in standby mode, waiting for an active interface to fail.)


show etherchannel summary
## 2.5 Interpret basic operations of Rapid PVST+ Spanning Tree Protocol
STP (Spanning Tree Protocol) prevents Layer 2 loops by placing redundant ports in a blocking state, essentially disabling the interface.
These interfaces act as backups that can enter a forwarding state if an active (=currently forwarding) interface fails.
Interfaces in a blocking state only send or receive STP messages (called BPDUs = Bridge Protocol Data Units)
Cisco switches use a version of STP called PVST+ (Per-VLAN Spanning Tree), which runs a seperate STP 'instance' in each VLAN, so in each VLAN different interfaces can be forwarding/blocking. This allows for load balancing by blocking different ports in each VLAN.
Rapid PVST+ allows for much faster converging/adapting to network changes, similar to 802.1w (Rapid Spanning Tree Protocol).
show spanning-tree

### 2.5.a Root port, root bridge (primary/secondary), and other port names
Switches use one field in the STP BPDU, the Bridge ID field, to elect a root bridge for the network.
The switch with the lowest Bridge ID becomes the root bridge. the default bridge priority is 32768 on all switches, so by default the MAC address is used as the tie-breaker (lowest MAC address becomes the root bridge). All ports on the root bridge are designated ports. Ports across from the root port are always designated ports. 
Each remaining switch will select ONE of its interfaces to be its root port. 
    Root port selection:
    1. Lowest root constructrs
    2. Lowest neighbor bridge ID
    3. Lowest neighbor port ID.

Each remaining collisions Domain will select ONE interface to be a designated port (forwarding state). The other port in the collision domain will be non-desingated (blocking).
    Designated port selection:
    1. Interface on switch with the lowest root cost
    2. Interface on switch with the lowest bridge ID
In RSTP, the non-designated port is split into two seperate roles:
    -the alternate port role (blocking)
    -the backup port role (two interfaces on same collision domain, via a hub)


spanning-tree vlan 10 root primary/secondary
    root primary = STP priority 24576
    root secondary = STP priority 28672

### 2.5.b Port states (forwarding/blocking)
Root/Designated ports remain stable in a Forwarding state.
Non-designated ports remain stable in a Blocking state. Interfaces in a Blocking state are effectively disabled to prevent loops.
Listening and Learning are transitional states which are passed through when an interface is activated, or when a Blocking port must transition to a Forwarding state due to a change in the network topology.
### 2.5.c PortFast
Spanning tree timer picture

Portfast allows a port to move immediately to the Forwarding state, bypassing Listening and Learning. If used, it must be enabled only on ports connected to end hosts. If enabled on a port connected to another switch it could cause a Layer 2 loop.

BPDU guard is another optional STP feature
    -can be used to prevent an access port from participating in the spanning tree.
SW1(config-if)#spanning-tree portfast (default)

## 2.6 Describe Cisco Wireless Architectures and AP modes

## 2.7 Describe physical infrastructure connections of WLAN components (AP, WLC, access/trunk ports, and LAG)

## 2.8 Describe AP and WLC management access connections (Telnet, SSH, HTTP, HTTPS, console, and TACACS+/RADIUS)

## 2.9 Interpret the wireless LAN GUI configuration for client connectivity, such as WLAN creation, security settings, QoS profiles, and advanced settings

## 3.0 IP Connectivity
Routers can use dynamic routing protocols to advertise information about the routes they know to other routers.
They form 'adjacencies' / 'neighbor relationships' / 'neighborships' with adjacent routers to exchange this information.
If multiple routes to a destination are learned, the router determines which route is superior and adds it to the routing table. It uses the 'metric' of the route to decide which is superior (lower metric = superior).
Dynamic routing protocols can be divided into two main categories:
    IGP (Interior Gateway Protocol)
        - used to share routes wihin a single autonomous system (AS), which is a single organization (ie. a company)
        - ex. RIP (Routing Information Protocol), EIGRP (Enhanced Interior Gateway Routing Protocol) using a Distance Vector algo
        - ex. OSPF (Open Shortest Path First) and IS-IS (Intermediate System to Intermediate System) (IS-IS) using a Link State algo 
    EGP (Exterior Gateway Protocol)
        - used to share routes between different autonomous systems
        - ex. BGP (Border Gateway Protocol) using a Path Vector algo

## 3.1 Interpret the components of routing table

### 3.1.a Routing protocol code
### 3.1.b Prefix
### 3.1.c Network mask
### 3.1.d Next Hop
### 3.1.e Administrative distance
In most cases a company will only use a single IGP, usually OSPF or EIGRP.
However, in some rare cases they might use two. For example, if two companies connect their networks to share information, two different routing protocols might be in use. 
Metric is used to compare routes learned via the same routing protocol. Different routing protocls use different metrics, so they cannot be compared. Instead, the AD (Administrative Distance) is used to determine which routing protocol is preferred.
A lower AD is preferred, and indicates that the routing protocol is considered more trustworthy (more likely to select good routes).

picture --------------
### 3.1.f Metric
A router's route table contains the best route to each destination network it knows about.
If a router using a dynamic routing protocol learns two different routes to the same destination, how does it determine which is 'best'?
It uses the metric value of the routes to dtermine which is best. A lower metric = better.
Each routing protocol uses a different metric to determine which route is best.
If a router learns two (or more) routes via the same routing protocol to the same destination (same network address, same subnet mask) with the same metric, both will be added to the routing table. Traffic will be load-balanced over both routes.
ECMP (Equal Cost Multi-Path)

picture --------------
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
A route to a network/subnet (mask length < /32)
### 3.3.c Host route
A route to a specific host (/32 mask)
### 3.3.d Floating static
By changing the AD of a static route, you can make it less preferred than routes learned by a dynamic routing protocl to the same destination (make sure the AD is higher than the routing protocol's AD!) This is known as a "floating static route".
The route will be inactive (not in the routing table) unless the route learned by the dynamic routing protocol is removed.


## 3.4 Configure and verify single area OSPFv2
OSPF uses shortest path first algorithm, aka Dijkstra's algorithm
Routers store information about the network in LSAs (Link State Advertisements), which are organized in a structure called the LSDB (Link State Database)
Routers will flood LSAs until all routers in the OSPF area develop the same map of the network (LSDB).
### 3.4.a Neighbor adjacencies
In OSPF, there are three main steps in the process of sharing LSAs and determining the best route to each destination in the network.
    1. Become neighbors with other routers connected to the same segment
    2. Exchange LSAs with neighbor routers
    3. Calculate the best routes to each destination, and insert them into the routing table
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

