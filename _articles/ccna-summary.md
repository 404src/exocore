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
PoE (Power over Ethernet) allows Power Sourcing Equipment (PSE) to provide power to Powered Devices (PD) over an Ethernet cable. 
Typically the PSE is a switch and the PDs are IP phones, IP cameras, wireless access points, etc.
The PSE receives AC power from the outlet, converts it to DC power, and supplies that DC power to the PDs.
PoE has a process to determine if a connected devices needs power, and how much power it needs, as too much current can damage devices.


## 1.2 Describe characteristics of network topology architectures

### 1.2.a 2-tier
The two-tier LAN design consists of two hierarchical layers:
    - Access Layer
    - Distribution Layer

Also called a 'Collapsed Core' design because it omits a layer that is found in the 3-Tier design: the Core Layer.
Access Layer:
    - the layer that end hosts connect to (PCs, printers cameras, etc.)
    - typically Access Layer Switches have lots of ports for end hosts to connect to
    - QoS marking is typically done here
    - Security sevices like port security, DAI, etc are typically performed here
    - switchports might be PoE-enabled for wireless APs, IP phones, etc.
Distribution Layer (sometimes called Aggregation Layer):
    - aggregates connections from the Access Layer Switches
    - typically is the border between Layer 2 and Layer 3
    - connects to services such as Internet, WAN, etc.


### 1.2.b 3-tier
In large LAN networks with many Distribution Layer switches (for example in separate buildings), the number of connections required between Distribution Layer switches grows rapidly. 
To help scale large LAN networks, you can add a Core Layer. Cisco recommends adding a Core Layer if there are more than three Distribution Layers in a single location.

The three-tier LAN design consists of three hierarchical layers:
- Access Layer
- Distribution Layer
- Core Layer

Core Layer:
- Connects Distribution Layers together in large LAN networks
- The focus is speed ('fast transport')
- CPU-intensive operations such as security, QoS marking/classification, etc. should be avoided at this Layer
- Connections are all Layer 3. No spanning-tree!
- Should maintain connectivity throughout the LAN even if devices fail
### 1.2.c Spine-leaf
Data centers are dedicated spaces/buildings used to store computer systems such as servers and network devices.
Traditional data center designs used a three-tier architecture (Access-Distribution-Core) shown previously.
This worked well when most traffic in the data center was North-South.
With the precedence of virtual servers, applications are often deployed in a distributed manner (across multiple physical servers), which increases the amount of East-West traffic in the data center.
The traditional three-tier architecture led to bottlenecks in bandwidth as well as variablility in the server-to-server latency depending on the path the traffic takes.
To solves this, Spine-Lead architecture (also called Clos architecture) has become prominent in data centers.

There are some rules about Spine-Leaf architecture:
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
TCP (Transmission Control Protocol)
- TCP is connection-oriented
      - Before actually sending data to the destination host, the two hosts commmunicate to establish a connection.
- TCP provides reliable communication.
    - The destination hsot must acknowledge that it received each TCP segment.
    - If a segment isn't acknowledged, it is sent again.
- TCP provides sequencing
    - Sequence numbers in the TCP header allow destination hosts to put segments in the correct order even if they arrive out of order.
- TCP provides flow control
    - The destination host can tell the source host to increase/decrease the rate that data is sent.

UDP (User Datagram Protocol.)

- UDP is not connection-oriented
  - The sending host does not establish a aconnection with the destination host before seinding data. The data is simply sent.
- UDP does not provide reliable communication
  - When UDP is used, acknowledgments are not sent for received segments. If a segment is lost, UDP has no mechanism to re-transmit it. Segments are sent "best-effort".
- UDP does not provide sequencing.
  - There is no sequence number field in the UDP header. If segments arrive out of order, UDP has no mechanism to put them back in order.
- UDP does not provide flow control
  - UDP has no mechanism like TCP's window size to control the flow of data.
  
Comparing TCP & UDP
  - TCP provides more features than UDP, but at the cost of additional overhead.
  - For applications that require reliable communications (for example downloading a file), TCP is preferred.
  - For applications like real-time voice and video, UDP is preferred.
  - There are some applications that use UDP, but provide reliability etc within the application itself.
  - Some applications use both TCP & UDP, depending on the situation.
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
IPv4 doesn't provide enough addresses for all devices that need an IP address in the modern world. The long term solutionn is to switch to IPv6.
There are three main short-term solutions:
    1. CIDR
    2. Private IPv4 addresses
    3. NAT
Private IPv5 address ranges:
    - 10.0.0.0/8 (10.0.0.0 to 10.255.255.255) (Class A)
    - 172.16.0.0/12 (172.16.0.0 to 172.31.255.255) (Class B)
    - 192.168.0.0/16 (192.168.0.0 to 192.168.255.255) (Class C)
These addresses are free to be used in networks. They don't have to be globally unique. Because private IPv4 addresses can't be used over the Internet, so the PCs can't access the Internet without NAT.
## 1.8 Configure and verify IPv6 addressing and prefix
config pic

## 1.9 Describe IPv6 address types
An IPv6 address is 128 bits written in hexadecimal.
### 1.9.a Unicast (global, unique local, and link local)
Global unicast ipv6 addresses are public addresses which can be used over the Internet.
        Must register to be used. Because they are public addresses, it is expected that they are globally unique.
        Originally defined as 2000::/3 block, now defined as all addresses which aren't reserved for other purposes.

Unique local IPv6 addresses are private addresses which cannot be used over the Internet.
        Does not need to be registered. They can be used freely within internal networks and don't need to be globablly unique. Can't be routed over the Internet.
        Uses address block FD00::/7

Link-local IPv6 addresses are automatically generated on IPv6-enabled interfaces. Use command R1(config-if)#ipv6 enable on an interface to enable IPv6 on that interface
        Uses address block FE80:://10
        The interface ID is generated using EUI-64 rules.
        Link-local means that these addresses are used for communication within a single link (subnet). Routers will not route packets with a link-local destination IPv6 address.
        Common uses of link-local addresses:
            - routing protocl peerings (OSPFv3 uses link-local addresses for neighbor adjacencies)
            - next-hop addresses for static routes
            - Neighbor Discovery Protocol (NDP, IPv6's replacement for ARP) uses link-local addresses to function
### 1.9.b Anycast
Anycast is a new feature of IPv6.
Anycast is "one-to-one-of-many"
Multiple routers are configured with the same IPv6 address. 
    - They use a routing protocol to advertise the address.
    - When hosts sends packets to that destination address, routers will forward it to the nearest router configured with that IP address (based on routing metric).
    - There is no specific address range for anycast addresses. Use a regular unicast address (global unicast, unique local) and specify it as an anycast address:
        - R1(config-if)# ipv6 address (ipv6 address)/128 anycast


### 1.9.c Multicast
Unicast addresses are one-to-one
    - one source to one destination
Broadcast addresses are one-to-all
    - one source to all destinations (within the subnet).
Multicast addresses are one-to-many.
    - one source to multiple destinations (that have joined the specific multicast group).
IPv6 uses range FF00::/8 for multicast. 
IPv6 doesn't use broadcast (there is no "broadcast address" in IPv6).

IPv6 defines multiple multicast "scopes" which indicate how far the packet should be forwarded. The addresses in the previous slide all use the "link-local" scope (FF02), which stays in the local subnet.
IPv6 multicast scopes:
    - Interface-local (FF01): The packet doesn't leave the local device. Can be used to send traffic to a service within the local device.
    - Link-local (FF02): The packet remains in the local subnet. Routers will not route the packet between subnets. 
    - Site-local (FF05): The packet can be forwarded by routers. Should be limited to a single physical location (not forwarded over a WAN)
    - Organization-local (FF08): Wider in scope than site-local (an entire company/organization).
    - Global (FF0E): No boundaries. Possible to be routed over the Internet.
### 1.9.d Modified EUI 64
EUI stands for Extended Unique Identifier
Modfied EUI-64 is a method of converting a MAC address (48 bits) into a 64-bit interface Identifier
This interface identifier can then become the "host portion" of a /64 IPv6 address.
To convert the MAC address:
    1. Split the MAC address into two halves
    2. Insert FFFE in the middle
    3. Invert the 7th bit
## 1.10 Verify IP parameters for Client OS (Windows, Mac OS, Linux)
>ipconfig /all

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
An access port is a switchport which belongs to a single VLAN, and usually connects to end hosts like PCs.
IP phones have an internal 3-port switch
    - 1 port is the 'uplink' to the external switch
    - 1 port is the 'downlink' to the PC
    - 1 port connects internally to the phone itself
This allows the PC and the IP phone to share a single switch port. Traffic from the PC passes through the IP phone to the switch.
It is recommended to seperate 'voice' traffic (from the IP phone) and 'data' traffic (from the PC) by placing them in seperate VLANs.
    - This can be accomplished using a voice VLAN
    - Traffic from the PC will be untagged, but traffic from the phone will be tagged with a VLAN ID.
  

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
Layer 2 discovery protocols such as CDP and LLDP share information with and discover information about neighboring (connected) devices. 
The shared information includes host name, IP address, device type, etc.
Because they share information about the devices in the network, they can be considered a security risk and are often not used. It is up to the network engineer/admin to decide if they want to use them in the network or not.
CDP (Cisco Discovery Protocol)
    It is enabled on Cisco devices (routers, switches, firewalls, IP phones, etc) by default.
    CDP messages are periodically sent to multicast MAC address 0100.0CCC.CCCC.
    When a device receives a CDP message, it processes and discards the message. It does NOT forward it to other devices.
    By default, CDP messages are sent once every 60 seconds. By default, the CDP holdtime is 180 seconds. If a message isn't received from a neighbor for 180 seconds, the neighbor is removed from the CDP neighbor table. 
    CDPv2 messages are sent by default.

LLDP (Link Layer Discovery Protocol)
    LLDP is an industry standard protocol (IEEE 802.1AB)
    It is usually disabled on Cisco devices by default, so it must be manually enabled.
    A device can run CDP and LLDP at the same time.
    LLDP messages are periodically sent to multicast MAC address 0180.C200.000E.
    When a device receives an LLDP message, it processes and discards the message. It does NOT forward it to other devices.
    By default, LLDP messages are sent once every 30 seconds. By default, the LLDP holdtime is 120 seconds.
    LLDP has an additional timer called the "reinitialization delay". If LLDP is enabled (globally or on an interface), this timer will delay the actual initialization of LLDP. 2 seconds by default. 


pictures of commands etc

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
IPv6 routing works the same as IPv4 routing.
However, the two processes are seperate on the router, and the two routing tables are seperate as well.
IPv4 routing is enabled by default. IPv6 routing is disabled by default, and must be enabled with "ipv6 unicast-routing"
If IPv6 routing is disabled, the router will be able to send and receive IPv6 traffic, but will not route IPv6 traffic (=will not forward it between networks).
A connected network route is automatically added for each connected network. A local host route is automatically added for each address configured on the router. Routes for link-local addresses are not added to the routing table.



to configure: 
ip route (destination ip address) (mask) (next-hop ip address)
ip route (destination-address) (mask) (exit-interface)
to verify: 
show ip route

### 3.3.a Default route
A route that a router uses to forward an incoming packet when no other route is available for that packet in the routing table.
### 3.3.b Network route
A route to a network/subnet (mask length < /32)
### 3.3.c Host route
A route to a specific host (/32 mask)

-example picture---
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

OSPF Neighbor requirements
    1. Area number must match
    2. Interfaces must be in the same subnet
    3. OSPF process must not be shutdown
    4. OSPF Router IDs must be unique
    5. Hello and Dead timers must match
    6. Authentication settings must match
    7. IP MTU settings must match (can become neighbors, but OSPF doesn't operate properly)
    8. OSPF network type must match (can become neighbors, but OSPF doesn't operate properly)
### 3.4.b Point-to-point
Point-to-point network type is enable on serial interfaces using the PPP or HDLC encapsulations by default.
Routers dynamically discover neighbors by sending/listening for OSPF Hello messages using multicast address 224.0.0.5.
A DR and BDR are not elected. The two routers will form a Full adjacency with eachother.
### 3.4.c Broadcast (DR/BDR selection)
Broadcast network type is enabled on Ethernet and FDDI interfaces by default.
Routers dynamically discover neighbors by sending/listening for OSPF Hello messages using multicast address 224.0.0.5. To send routing information to a DR or BDR the multicast address of 224.0.0.6 is used.

A DR (designated router) and BDR (backup designated router) must be elected on each subnet (only DR if there are no OSPF neighbors)
Routers which aren't the DR or BDR become a DROther.

The DR/BDR election order of Priority:
    1. Highest OSPF interface priority
    2. Highest OSPF Router ID
"First place" becomes the DR for the subnet, "second place" becomes the BDR
The default OSPF interface priority is 1 on all interfaces.
In the broadcast network type, routers will only form a full OSPF adjacency with the DR and BDR of the segment. Therefore, routers only exchange LSAs with the DR and BDR. DROthers will not exchange LSAs with each other. All routers will still have the same LSDB, but this reduces the amount of LSAs flooding the network.
### 3.4.d Router ID
OSPF uses the largest IP address configured on the interfaces as its router ID. If a loopback interface is configured with an IP address, the Cisco IOS software will use this IP address as its router ID.

## 3.5 Describe the purpose, functions, and concepts of first hop redundancy protocols
A (FHRP) First Hop Redundancy Protocol is a computer networking protocol which is designed to protect the default gateway used on a subnetwork by allowing two or more routers to provide backup for the gateway address; in the event of failure of an active router, the backup router will take over the address, usually within a few seconds.
A virtual IP is configured on the two routers, and a virtual MAC is generated for the virtual IP (each FHRP uses a different format for the virtual MAC)
An active router and a standby router are elected. (different FHRPs use different terms)
End hosts in the network are configured to use the virtual IP as their default gateway.
The active router replies to ARP requests using the virtual MAC address, so traffic destined for other networks will be sent to it.
If the active router fails, the standby becomes the next active router. The new active router will send gratuitous ARP messages so that switches will update their MAC address tables. It now functions as the default gateway.
If the old active router comes back online, by default it won't take back its role as the active router. It will become the standby router ("non-preemptive")
Preemption can be configured, so the old router does take back its old role.
List of FHRPs:
    1. HSRP (Hot Standby Router Protocol) 
    2. VRRP (Virtual Router Redundancy Protocol) 
    3. GLBP (Gateway Load Balancing Protocol) 
   

## 4.0 IP Services


## 4.1 Configure and verify inside source NAT using static and pools
NAT (Network Address Translation) is used to modify the source and/or destination IP addresses of packets. 
There are various reasons to use NAT, but the most common reason is to allow hosts with private IP addresses to communicate with other hosts over the Internet.
Static NAT involves statically configuring one-to-one mappings of private IP addresses to public IP addresses. 
An inside local IP address is mapped to an inside global IP address.
    - Inside Local: The IP address of the inside host, from the perspective of the local network. (The IP address actually configured on the inside host, usually a private address)
    - Inside Global: The IP address of the inside host, from the perspective of outside hosts (the IP address of the inside host after NAT, usually a public address)
- conf picture-
In dynamic NAT, the router dynamically maps inside local addresses to inside global addresses as needed. 
An ACL is used to identify which traffic should be translated.
    - If the source IP is permitted by the ACL, the soruce IP will be translated.
    - If the soruce IP is denied by the ACL, the source IP will NOT be translated. (the traffic will NOT be dropped!)
A NAT pool is used to define the available inside global addresses that can be used.
Although they are dynamically assigned, the mappings are still one-to-one (one inside local IP address per inside global address)
If there arent enough inside global IP address available (=all are currently being used), it is called 'NAT pool exhaustion'
      - If a packet from another inside host arrives and needs NAT but there are no available addresses, the router will drop the packet.
      - The host will be unable to access outside networks until one of the inside global IP addresses becomes available.
      - Dynamic NAT entries will time out automatically if not used, or you can clear them manually. 
## 4.2 Configure and verify NTP operating in a client and server mode
NTP (Network Time Protocol) allows automatic syncing of time over a network. 
    NTP clients request the time from NTP servers.
    A device can be an NTP server and an NTP client at the same time.
    NTP allows accuracy of time within ~1 millisecond if the NTP server is in the same LAN, or within ~50 milliseconds if connecting to the NTP server over a WAN/the Internet.
    Some NTP servers are 'better' than others. The 'distance' of an NTP server from the orginal reference clock is called stratum.
    Reference clock is usually a very accurate time device like an atomic clock or a GPS clock.
    Reference clocks are stratum 0 within the NTP hierarchy. NTP servers directly connected to reference clocks are stratum 1 (primary servers). NTP servers that get their time from stratum 1 NTP servers are stratum 2 (secondary servers). Stratum 15 is the maximum.
    An NTP client can sync to multiple NTP servers.
    Devices can also 'peer' with devices at the same stratum to provide more accurate time. This is called 'symmetric active' mode.
    Cisco devices can operate in three NTP modes:
        - Server mode
        - Client mode
        - Symmetric active mode
    NTP uses UDP port 123 to communicate.
    NTP uses only the UTC time zone. You must configure the appropriate time zone on each device.

## 4.3 Explain the role of DHCP and DNS within the network
DNS (Domain Name System) is used to resolve human-readable names (google.com) to IP addresses.
When you type 'youtube.com' into a web browser, your device will ask a DNS server for the IP address of youtube.com.
The DNS server(s) your device uses can be manually configured or learned via DHCP.
Standard DNS queries/responses typically use UDP. TCP is used for DNS messages greater than 512 bytes. In either case, port 53 is used.
Devices will save the DNS server's responses to a local DNS cache. This means they don't have to query the server every single time they want to access a particular destination. 
>ipconfig /displaydns
>nslookup youtube.com

DHCP (Dynamic Host Configuration Protocol)
    DHCP is used to allow hosts to automatically/dynamically learn various aspects of their network configuration, such as IP address, subnet mask, default gateway, DNS server, etc, without manual/static configuration.
    It is an essential part of modern networks. Typically used for 'client devices' such as workstations (PCs), phones, etc.
    Devices such as routers, servers, etc, are usually manually configured. 
    In small networks (such as home networks) the router typically acts as the DHCP server for hosts in the LAN. 
    In larger networks, the DHCP server is usually a Windows/Linux server.

## 4.4 Explain the function of SNMP in network operations
SNMP (Simple Network Management Protocol) helps manage devices over a network.
Managed Devices are the devices being managed using SNMP, such as network devices (routers, switches, firewalls)
Network Management Stations (NMS) are the SNMP 'servers' that manage the devices. 
    - NMS receives notifications from managed devices
    - NMS changes settings on managed devices
    - NMS checks status of managed devices
Variables such as interface status, temperature, traffic load, host name, etc. are stored in the Management Information Base (MIB) and identified using Object IDs (OIDs)
Main SNMP versions: SNMPv1, SNMPv2c, SNMPv3
SNMP messages: Get, GetNext, GetBulk, Set, Trap, Inform, Response
There are three main operations used in SNMP.
    1. Managed devices can notify the NMS of events
    2. The NMS can ask the managed devices for information about their current status.
    3. The NMS can tell the managed devices to change aspects of their configuration.
## 4.5 Describe the use of syslog features including facilities and levels
Syslog is an industry standard protocol for message logging.
On network devices, Syslog can be used to log events such as changes in interface status (up<->down), changes in OSPF neighbor status, system restarsts, etc.
The messages can be displayed in the CLI, saved in the device's RAM, or sent to an external Syslog server.
Logs are essential when troubleshooting issues, examining the cause of incidents, etc.
Syslog and SNMP are both used for monitoring and troubleshooting of devices. They are complementary, but their functionalities are different.
## 4.6 Configure and verify DHCP client and relay
-pictures-
## 4.7 Explain the forwarding per-hop behavior (PHB) for QoS, such as classification, marking, queuing, congestion, policing, and shaping 
QoS is used to manage the following characteristics of network traffic:
    1. Bandwidth
    2. Delay
    3. Jitter
    4. Loss
The following standards are recommended for acceptable interactive audio quality:
   - One-way delay: 150ms or less
   - Jitter: 30 ms or less
   - Loss: 1% or less

If a network device receives messages faster than it can forward them out of the appropriate interface, the messages are placed in a queue.
By default, queued messages will be forwarded in a First In First Out (FIFO manner)
    - Messages will be sent in the order they are received.
If the queue is full new packets will be dropped, this is known as tail drop.
Tail drop is harmful because it can lead to TCP global synchronization causing all TCP hosts sending traffic to slow down the rate at which they send traffic, followed by all hosts increasing the rate at which they send traffic, rapidly leading to more congestion, dropped packets, and the process repeating again.
A solution to prevent tail drop and TCCP global synchronization is Random Early Detected (RED).
    - When the amount of traffic in the queue reaches a certain threshold, the device will start randomly dropping packets from select TCP flows.
    - In standard RED, all kinds of traffic are treated the same.
    - An improved version, WREDD (Weighted Random Early Detection) allows you to control which packets are dropped depending on the traffic class.
    - 



## 4.8 Configure network devices for remote access using SSH
SSH (Secure Shell) allows for remote access while providing security features such as  data encryption and authentication. 
The SSH server (the device being connected to) listens for SSH traffic on TCP port 22.
To enable and use SSH, you must generate an RSA public and private key pair. The keys are used for data encryption/decryption, authentication, etc.
-picture-
## 4.9 Describe the capabilities and function of TFTP/FTP in the network
FTP (File Transfer Protocol) and TFTP (Trivial File Transfer Protocol) are industry standard protocols used to transfer files over a network.
They both use a client-server model.
    - Clients can use FTP or TFTP to copy files from a server.
    - Clients can use FTP or TFTP to copy files to a server.
As a network engineer, the most common use for FTP/TFTP is in the process of upgrading the operating system of a network device. You can use FTP/TFTP to download the newer version of IOS from a server, and then reboot the device with the new IOS image.
FTP uses usernames and passwords for authentication, however there is no encryption.
    - FTP uses TCP ports 20 and 21. 
    - For greater security, FTPS (FTP over SSL/TLS) can be used.
    - SSH File Transfer Protocol (SFTP) can also be used for greater security (new protocol)
    - FTP is more complex than TFTP and allows not only file transfers, but clients can also navigate file directories, add and remove directories, list files, etc.
    - The client sends FTP commands to the server to perform these functions.

TFTP is named trivial because it is simple and has only basic features compared to FTP. 
    - Only allows a client to copy a file to or from a server.
    - Released after FTP, but not a replacement for FTP. It is another tool to use when lightweight simplicity is more important than functionality.
    - No authentication, servers will respond to all TFTP requests. No encryption, so all data is sent in plain text.
    - Best used in a controlled environment to transfer small files quickly.
    - TFTP servers listen on UDP port 69.
    - UDP is connectionless and doesn't provide reliability with retransmissions, however, TFTP has similar built-in features within the protocol itself.
    - TFTP uses 'lock-step' communication. The client and server alternately send a message and then wait for a reply. (+retransmissions are sent as needed)

## 5.0 Security Fundamentals
The principles of the CIA Triad form the foundation of security:

Confidentiality
    - only authorized users should be able to access data.
    - some information/data is public and can be accessed by anyone, some is secret and should only be accessed by specific people.
Integrity
    - Data should not be tampered with (modified) by unauthorized users.
    - Data should be correct and authentic.
Availability
    - The network/system should be operational and accessible to authorized users.
## 5.1 Define key security concepts (threats, vulnerabilities, exploits, and mitigation techniques)
A vulnerability is any potential weakness that can compromise the CIA of a system/info.
    - a potential weakness isn't a problem on its own
An exploit is something that can potentially be used to exploit the vulnerability.
    - something that can potentially be used as an exploit isn't a problem on its own
A threat is the potential of a vulnerability to be exploited.
    - A hacker exploiting a vulnerability in your system is a threat.
A mitigation technique is something that can protect against threats.
    - Should be implemented everywhere a vulnerability can be exploited: client devices. servers, switches, routers, firewalls, etc.
## 5.2 Describe security program elements (user awareness, training, and physical access control)
User awareness programs are designed to make employees aware of potential security threats and risks.
    - For example, a company might send out false phishing emails to make employees click a link and sign in with their login credentials.
    - Although the emails are harmless, employees who fall for the false emails will be informed that it is part of a user awareness program and they should be more careful about phishing emails.
User training programs are more formal than user awareness programs.
    - For example, dedicated training sessions which educate users on the corporate secuirty policies, how to create strong passwords, and how to avoid potential threats.
Physical access control protects equipment and data from potential attackers by only allowing authorized users into protected areas such as network closets or data center floors.
    - Multifactor locks can protect access to restricted areas.
    - ie. a door that requires users to swipe a badge and scan their fingerprint to enter.
    - Permissions of the badge can easily be changed, for example permissions can be removde when an employee leaves the company.
## 5.3 Configure and verify device access control using local passwords

## 5.4 Describe security password policies elements, such as management,complexity, and password alternatives (multifactor authentication, certificates, and biometrics)
Multi-factor authentication involves providing more than just a username/password to prove your identity. It usually involves providing two (or more) of the following:
    - Something you know
        - a username/password combination, a PIN, etc.
    - Something you have
        - pressing a notification that appears on your phone, a badge that is scanned, etc.
    - Something you are
        - biometrics such as a face scan, palm scan, fingerprint scan, retina scan, etc.
Requiring multiple factors of authentication greatly increases the security.

Digital certificates are another form of authentication used to prove the identity of the holder of the certificate. They are used for websites to verify that the website being accessed is legitimate.
Entities that want a certificate to prove their identity send a CSR (Certificate Signing Request) to a CA (Certificate Authority), which will generate and sign the certificate.
## 5.5 Describe IPsec remote access and site-to-site VPNs
## 5.6 Configure and verify access control lists
ACLs (Access Control Lists) function as a packet filter, instructing the router to permit or discard specific traffic. 
ACLs can filter traffic based on source/destination IP addresses, source/destination IP addresses, source/destination Layer 4 ports, etc.
ACLs are configured globally on the router, and consist of an ordered sequence of ACEs (Access Control Entries)
Configuring an ACL will not make the ACL take effect, the ACL must be applied to an interface. ACLs are applied either inbound or outbound.
If the packet matches one of the ACEs in the ACL, the router takes the action and stops processing the ACL, all entries below the matching entry will be ignored. 
There is an implicit deny at the end of all ACLs. The implicit deny tells the router to deny all traffic that doesn't match any of the configured entries in the ACL.
Standard ACLs: Match based on the Source IP address only.
    Standard ACLs can use 1-99 and 1300-1999.
    Standard ACLs should be applied as close to the destination as possible.
    R1(config)# access-list (#) (deny/permit) (ip) (wildcard-mask)
    R1(config-if)# ip access-group (#) (in/out)
Extended ACLs: Match based on Source/Destination IP, Source/Destination port/protocol, etc
    Extended ACLs can use 100-199, 2000-2699.
    Extended ACLs should be appleid as close to the source as possible.
    R1(config)# access-list (#) (permit/deny) (protocol) (src-ip) (dest-ip)
    R1(config)# ip access-list extended (name/number)
    R1(config-ext-nacl)# (seq-num) (permit/deny) (protocol) (src-ip) (dest-ip)

## 5.7 Configure and verify Layer 2 security features (DHCP snooping, dynamic ARP inspection, and port security)
DHCP snooping is security feature of switches that is used to filter DHCP messages received on untrusted ports.
DHCP snooping only filters DHCP messages. Non-DHCP messages aren't affected.
All ports are untrusted by default.
    - Usually, uplink ports are configured as trusted ports, and downlink ports remain untrusted.


Dynamic ARP inspection (DAI) is a security feature of switches that is used to filter ARP messages received on untrusted ports.
DAI only filters ARP messages. Non-ARP messages aren't affected.
All ports are untrusted by default.
    - Typically, all ports connected to other network devices (switches, routers) should be configured as trusted, while itnerfaces connected to end hosts should remain untrusted.

Port security is a security feature of Cisco switches. It allows you to control which source MAC address(es) are allowed to enter the switchport.
If an authorized source MAC address enters the port, an action will be taken.
    - The default action is to place the interface in an 'err-disabled' state.
When you enable port security on an interface with the default settings, one MAC Addres is allowed.
    - You can configure the allowed MAC address manually.
    - If you don't configure it manually, the switch will allow the first source MAC address that enters the interface.
    - You can change the maximum number of MAC addresses allowed
    - A combination of manually configured MAC addresses and dynamically learned addresses is possible.


## 5.8 Compare authentication, authorization, and accounting concepts
AAA (triple-A) stands for Authentication, Authorization, and Accounting. 
It is a framework for controlling and monitoring users of a computer system (ie. a network)

Authentication is the process of verifying a user's identity.
    - logging in = authentication
Authorization is the process of granting the user the appropriate access and permissions.
    - granting the user acces to some files/services, restricting access to other files/services = authorization.
Accounting is the process of recording the user's activities on the system.
    - logging when a user makes a change to a file = accounting

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

