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
Network speed is measured in bits per second (Kbps, Mbps, Gbps, etc), not bytes per second.
- 1 kilobit (Kb) = 1,000 bits
- 1 megabit (Mb) = 1,000,000 bits
- 1 gigabit (Gb) = 1,000,000,000 bits
- 1 terabit (Tb) = 1,000,000,000,000 bits

![](/images/ethernetstandardscopper.png)
![](/images/fiberopticstandards.png)
![](/images/UTPvsFiberoptic.png)

OSI Model
- "Open Systems Interconnection" model
- A conceptual model that categorizes and standardizes the different functions in a network.
- Created by the "Internation Organization for Standardization" (ISO)
- Functions are divided into 7 "Layers"
- These layers work together to mae the network work.

Application Layer, Layer 7
- This layer is closest to the end user.
- Interacts with software applications, for example your web browser (Brave, Firefox, Chrome, etc)
- HTTP and HTTPS are Layer 7 protocols
- Functions of Layer 7 include:
    - Identifying communication partners
    - Synchronizing communication

Presentation Layer, Layer 6
- Data in the application layer is in 'application format'
- It needs to be 'translated' to a different format to be sent over the network
- The Presentation Layer's job is to translate between application and network formats.
- For example, encryption of data as it is sent, and decryption of data as it is received.
- Also translates between different Application-Layer formats.

Session Layer, Layer 5
- Controls dialogues (sessions) between communicating hosts.
- Establishes, manages, and terminates connections between the local application (for example, your web browser) and the remote application (for example, YouTube)

OSI Model - The Upper Layers (Layer 7, 6, 5)
- Network engeineers don't usually work with the top 3 layers.
- Application developers work with the top layers of the OSI model to connect their applications over networks.

Transport Layer, Layer 4
- Segments and reassembles data for communications between end hosts
- Breaks large pieces of data into smaller segments which can be more easily sent over the network and are less likely to cause transmission problems if errors occur
- Provides host-to-host communication
- uses layer 4 header (data + L4 header = segment)

Network Layer, Layer 3
- Provides connectivity between end hosts on different networks (ie. outside of the LAN)
- Provides logical addressing (IP addresses)
- Provides path selection between source and destination
- Routers operate at Layer 3.
- Uses Layer 3 header (data + L4 header + L3 header = packet)

Data Link Layer, Layer 2
- Provides node-to-node connectivity and data transfer (for example, PC to switch, switch to router, router to router)
- Defines how data is formatted for transmission over a physical medium (for example, copper UTP cables)
- Detects and (possibly) corrects Physical Layer errors
- Uses Layer 2 addressing, seperate from Layer 3 addressing.
- Switches operate at Layer 2.
- Uses L2 trailer and header (L2 trailer + Data + L4 header + L3 header + L2 header = frame)

Physical Layer, Layer 1
- Defines physical characteristics of the medium used to transfer data between devices.
- For example, voltage levels, maximum transmission distances, physical connectors, cable specifications, etc.
- Digital bits are converted into electrical (for wired connections) or radio (for wireless connections) signals.
- All of the information in regarding cables, pin layouts, etc. is related to the Phyiscal Layer.

Encapsulation - data moving from Layer 7 to Layer 1, the process of adding additional information when data is traveling in OSI or TCP/IP model. The additional information is added on the sender's side, starting from Application layer to Physical layer.

De-encapsulation - data moving from Layer 1 to 7, the process in which information added through the encapsulation process is removed. The additional information is removed (de-encapsulated) on the receiver's side, starting from the Physical layer to the Application layer. 

![](/images/OSI%20PDUs.png)
![](/images/OSIacronyms.png)

TCP/IP Suite
- Conceptual model and set of communications protocols used int the the Internet and other networks
- Known as TCP/IP because those are two of the foundational protocols in the suite.
- Developed by the United State Department of Defense through DARPA (Defense Advanced Research Projects Agency)
- Similar structure to the OSI Model, but with fewer layers.
- This is the model actually in use in modern networks.
- The OSI model still influences how network engineers think and talk about networks.

![](/images/OSIvstcpip.png)

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

Two-tier Campus LAN Design:
![](/images/two-tier%20campus%20LAN%20design.png)

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

Three-Tier Campus LAN Design:
![](/images/three-tier%20campus%20lan%20design.png)

### 1.2.c Spine-leaf
Data centers are dedicated spaces/buildings used to store computer systems such as servers and network devices.

Traditional data center designs used a three-tier architecture (Access-Distribution-Core) shown previously.

This worked well when most traffic in the data center was North-South.

With the precedence of virtual servers, applications are often deployed in a distributed manner (across multiple physical servers), which increases the amount of East-West traffic in the data center.

The traditional three-tier architecture led to bottlenecks in bandwidth as well as variablility in the server-to-server latency depending on the path the traffic takes.

To solves this, Spine-Lead architecture (also called Clos architecture) has become prominent in data centers.

There are some rules about Spine-Leaf architecture:
- Every Leaf switch is connected to every Spine switch
- Every Spine switch is connected to every Leaf switch
- Leaf switches do not connect to other Leaf switches
- Spine switches do not connect to other Spine switches 
- End hosts (servers etc.) only connect to Leaf switches

The path taken by traffic is randomly chosen to balance the traffic load among the Spine switches

Each server is separated by the same number of 'hops' (except those connected to the same Leaf), providing consistent latency for East-West traffic.
![](/images/spine-leaf.png)

### 1.2.d WAN
WAN (Wider Area Network) is a network that extends over a large geographic area.
WANs are used to connect geographically seperate LANs.
Although the Internet itself can be considered a WAN, the term WAN is typically used to refer to an enterprise's private connections that connect their offices, data centers, and other sites together.
Over public/shared networks like the Internet, VPNs (Virtual Private Networks) can be used to create private WAN connections.
There have been many different WAN technologies over the years. Depending on the location, some will be available and some will not be.
Technologies which are considered 'legacy' (old) in one country might still be used in other countries.

Private WAN services such as leased lines and MPLS provide security because each customer's traffic is seperated by using dedicated physical connections (leased line) or by MPLS tags.
![](/images/leasedlines.png)
![](/images/MPLS.png)

WAN Architectures:
![](/images/WANleasedline1.png)
![](/images/wanleasedline2.png)
![](/images/wanfiber.png)

To provide secure communications over the Internet, VPNs (Virtual Private Networks) are used.
![](/images/WANoverVPN.png)


### 1.2.e Small office/home office (SOHO)
SOHO (Small Office/Home Office) refers to the office of a small company, or a small home office with few devices.
- Doesn't have to be an actual home 'office', if your home has a network connected to the Internet it is considered a SOHO network.

SOHO devices don't have complex needs, so all networking functions are typically provided by a single device, often called a 'home router' or 'wireless router'

This one device can serve as a:
- Router 
- Switch
- Firewall
- Wireless Access Point
- Modem
![](/images/SOHO%20network.png)

### 1.2.f On-premise and cloud
Traditional IT infrastructure deployments were some combination of the following:

On-Premises
- All servers, network devices, and other infrastructure are located on company property.
- All equipment is purchased and owned by the company using it.
- The company is responsible for the necessary space, power, and cooling.

Colocation
- Data centers that rent out space for customers to put their infrastructure (servers, network devices)
- The data center provides the space, electricity, and cooling.
- The servers, network devices, etc are still the responsibility of the end customer, although they are not located on the customer's premises.

Cloud service provide an alternative that is hugely popular, and continuing to grow.
Most people associate 'cloud' with public cloud providers such as AWS, Microsoft Azure, GCP
- Although this is the most common use of cloud services, it's not the only one.

Cloud computing is defined by the American NIST in SP 800-145 as follows.
The five essential characeteristics of cloud computing are:
- On-demand self-service
    - A consumer can unilaterally provision computing capabilities, such as server time and network storage, as needed automatically without requiring human interaction with each service provider.
    - The customer is able to use the service (or stop using the service) freely (via a web portal) without direct communication to the service provider.
- Broad network access
    - Capabilities are available over the network and accessed through standard mechanisms that promote use by hereogeneous thin or thick client platforms (e.g mobile phones, tablets, laptops, and workstations).
    - The service is available through standard network connections (ie, the Internet or private WAN connections), and can be accessed through many kinds of devices.
- Resource pooling
    - A pool of resources is provided by the service provider, and when a customer requests a service (for example creates a new VM), the resources to fulfill that request are allocated from the shared pool.
- Rapid elasticity
    - Customers can quickly expand the services they use in the cloud (for example, add new VMs, expand storage, etc) from a pool of resources that appears to be infinite. Likewise, they can quickly reduce their services when not needed.
- Measured service
    - The cloud service provider measures the customer's usage of cloud resources, and the customer can measure their own use as well. Customers are charged based on usage (for example, X dollars per gigabyte of storage per day).

The three service models of cloud:
- Software as a Service (SaaS)
    - The capability provided to the consumer is to use the provider's applications running on a cloud infrastructure. The application are accessible from various client devices through either a thing client interface, such as a web browser (e.g. web-based email), or a program interface.
    - The consumer does not manage or control the underlying cloud infrastructure including network, servers, operating systems, storage, or even individual application capabilities, with the possible exception of limited user-specific application configuration settings. ex. Microsoft Office 365
- Platform as a Service (PaaS)
    - The capability provided to the consumer is to deploy onto the cloud infrastructure consumer-created or acquired applications creating using programming languages, libraries, services, and tools supported by the provider. 
    - The consumer does not manage or control the underlying cloud infrastructure including network, servers, operating systems, or storage, but has control over the deployed applications and possibly configuration settings for the application-hosting environment. ex. AWS Lambda and Google App Engine.
- Infrastructure as a Service (IaaS)
    - The capability provided to the consumer is to provision processing, storage, networks, and other fundamental computing resources where the consumer is able to deploy and run arbitrary software, which can include operating systems and applications.
    - The consumer does not manage or control the underlying cloud infrastrcture but has control over operating systems, storage, and deployed applications; and possibly limited control of select networking components (e.g. host firewalls).
    - Examples include Amazon EC2 and Google Compute Engine.

![](/images/saas.png)


The four deployment models of cloud:
- Most people assume that 'cloud' means public cloud providers such as AWS, Azure, and GCP.
- Although 'Public cloud' is the most common deployment model, it's not the only one.

The four deployment models of cloud computing are:
- Private cloud
    - The cloud infrastructure is provisioned for exclusive use by a single organization comprising multiple consumers (e.g. business units). It may be owned, managed, and operated by the organization, a third party, or some combination of them, and it may exist on or off premises.
    - Private clouds are generally only used by large enterprises.
    - Although the cloud is private, it may be owned by a third party.
        - For example, AWS provides private cloud services for the American DoD.
    - Private clouds may be on or off premises.
        - Many people assume that 'cloud' and 'on-prem' are two different things, but that is not always the case.
    - The same kinds of services offered are the same as in public clouds (Saas, PaaS, IaaS), but the infrastructure is reserved for a single organization

- Community cloud
    - The cloud infrastructure is provisioned for exclusive use by a specific community of consumers from organizations that have shared concerns (e.g. mission, security requirements, policy, and compliance considerations). It may be owned, managed, and operated by one or more of the organizations in the community, a third party, or some combination of them, and it may exist on or off premises.
    - This is the least common cloud deployment.
    - Similar to private cloud, but the infrastructure is reserved for use by only a specific group of organizations.

- Public cloud
    - The cloud infrastructure is provisioned for open use by the general public. It may be owned, managed, and operated by a business, academic, or government organization, or some combination of them. It exists on the premises of the cloud provider.
    - This is the most common cloud deployment.
    - Popular public cloud service providers include:
        - AWS (Amazon Web Services)
        - Microsoft Azure
        - GCP (Google Cloud Platform)
        - OCI (Oracle Cloud Infrastructure)
        - IBM Cloud
        - Alibaba Cloud

- Hybrid cloud
    - The cloud infrastructure is a composition of two or more distinct cloud infrastrctures (private, community, or public) that remain unique entities, but are bound together by standardized or proprietary technology that enables data and application portability (e.g. cloud bursting for load balancing between clouds).
    - This is basically any combination of the previous three deployment types.
    - For example, a private cloud which can offload to a public cloud when necessary.

Benefits of Cloud Compouting
- Cost
    - CapEx (Capital Expenses) of buying hardware and software, setting up data centers etc. are reduced or eliminated.
- Global Scale
    - Cloud services can scale globally at a rapid pace. Services can be set up and offered to customers from a geographic location close to them.
- Speed/Agility
    - Services are provided on demand, and vast amounts of resources can be provisioned within minutes.
- Productivity
    - Cloud services remove the need for many time-consuming tasks such as procuring physical servers, racking them, cabling, installing and updating operating systems, etc.
- Reliability
    - Backups in the cloud are very easy to perform. Data can be mirrored at multiple sites in different geographic locations to support disaster recovery.

![](/images/connectingtocloudresources.png)




## 1.3 Compare physical interface and cabling types
RJ-45 (RJ = Registered Jack) - Standard connector for copper UTP cables that has 8 pin connections.

UTP cables - Unshielded twisted pair copper wire, contains 4 pairs of wires twisted together, with 8 wires in total.
![](/images/UTP%20cable%20pins.png)

Straight-through cable - 
![](/images/straight-through%20cable.png)
Crossover cable - 
![](/images/crossover%20cable.png)
1000BASE-T, 10GBASE-T cabling - 
![](/images/bidirectional%20cabling.png)

Using Auto MDI-X, devices are able to automatically detect which pins their neighbor is using to transmit data and automatically adjust their pins to receive and transmit on the correct pins.

![](/images/ethernetstandardscopper.png)
![](/images/fiberopticstandards.png)
![](/images/UTPvsFiberoptic.png)


### 1.3.a Single-mode fiber, multimode fiber, copper
SFP Transceiver (SFP = Small Form-Factor Pluggable) - connector used for fiber-optic ports on a switch, connects to Fiber-Optic cabling.

Single-mode fiber is narrower than multimode fiber, light enters at a single angle (mode) from a laser-based transmitter. Allows for longer cables than both UTP and multimode fiber, but also more expensive.

Multimode fiber is wider than single-mode fiber, allows multiple angles (modes) of light waves to enter the fiberglass core. Allows longer cables than UTP, but shorter than single-mode fiber.

### 1.3.b Connections (Ethernet shared media and point-to-point)


## 1.4 Identify interface and cable issues (collisions, errors, mismatch duplex, and/or speed)
>show ip interface brief
- can be used to view interfaces (includes VLANs), IP addresses, OK?, method, status, and protocol status
>show interfaces status
- can be used to show port, name, status, VLAN, duplex, speed, type 

![](/images/configinterfaces.png)

CSMA/CD (Carrier Sense Multiple Access with Collision Detection)
- Before sending frames, devices 'listen' to the collision domain until they detect that other devices are not sending.
- If a collision does occur, the device sends a jamming signal to inform the other devices that a collision happened.
- Each device will wait a random period of time before sending frames again.
- The process then repeats.
- Typically only an issue in networks that use hubs (which are mostly obsolete today)
- Switches operate in full duplex, rather than half duplex like hubs.

Speed/Duplex Autonegotiation
- Interfaces that can run at different speed (10/100 or 10/100/1000) have default settings of speed auto and duplex auto.
- Interfaces 'advertise' their capabilities to the neighboring device, and they negotiate the best speed and duplex settings they are both capable of.
Ethernet - 10 Mbps
FastEthernet - 10/100 Mbps
GigabitEthernet - 10/100/1000 megabits/second Mbps

What is autonegotiation is disabled on the device connected to the switch?
- Speed: The switch will try to sense the speed that the otehr device is operating at.
    - If it failts to sense the speed, it will use the slowest supports speed (ie. 10 Mbps on a 10/100/1000 interface)
- Duplex: If the speed is 10 or 100 Mbps, the switch will use HALF duplex (BAD, will lead to misconfigurations). If the speed is 1000 Mbps or greater, use full duplex. 
- To avoid misconfigurations, use autonegotiation on ALL devices in the network.

Interface errors can be viewed by using #show interfaces f0/#
![](/images/interfaceerrors.png)

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

UDP (User Datagram Protocol)

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

![](/images/TCPvsUDP.png)
![](/images/TCPandUDPportnumbers.png)
## 1.6 Configure and verify IPv4 addressing and subnetting
![](/images/IPV4%20address%20classes.png)
![](/images/IPV4%20Addresses%20ABC.png)
Maximum number of hosts per network:
![](/images/Maximum%20hosts%20per%20network.png)
First/Last Usable Address:
![](/images/First/Last%20Usable%20Address.png)

CIDR (Classless Inter-Domain Routing) removed the previous requirements of:
    Class A = /8
    Class B = /16
    Class C = /24
This allows larger networks to be split into smaller networks, allowing greater efficiency.
These smaller networks are called "subnetworks" or "subnets".
![](/images/CIDR%20notation.png)

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
Configuring IPv6:
![](/images/configuring%20ipv6.png)
Verify IPv6:
![](/images/verify%20ipv6.png)

## 1.9 Describe IPv6 address types
An IPv6 address is 128 bits written in hexadecimal.
### 1.9.a Unicast (global, unique local, and link local)
Global unicast ipv6 addresses are public addresses which can be used over the Internet.
- Must register to be used. Because they are public addresses, it is expected that they are globally unique.
- Originally defined as 2000::/3 block, now defined as all addresses which aren't reserved for other purposes.

Unique local IPv6 addresses are private addresses which cannot be used over the Internet.
- Does not need to be registered. They can be used freely within internal networks and don't need to be globablly unique. Can't be routed over the Internet.
- Uses address block FD00::/7

Link-local IPv6 addresses are automatically generated on IPv6-enabled interfaces. Use command R1(config-if)#ipv6 enable on an interface to enable IPv6 on that interface
- Uses address block FE80:://10
- The interface ID is generated using EUI-64 rules.
- Link-local means that these addresses are used for communication within a single link (subnet). Routers will not route packets with a link-local destination IPv6 address.
- Common uses of link-local addresses:
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
![](/images/anycast%20address%20config.png)

### 1.9.c Multicast
Unicast addresses are one-to-one
- one source to one destination
Broadcast addresses are one-to-all
- one source to all destinations (within the subnet).
Multicast addresses are one-to-many.
- one source to multiple destinations (that have joined the specific multicast group).
IPv6 uses range FF00::/8 for multicast. 
IPv6 doesn't use broadcast (there is no "broadcast address" in IPv6).
![](/images/multicast%20ipv6.png)
verify multicast addresses:
![](/images/verify%20multicast.png)
IPv6 defines multiple multicast "scopes" which indicate how far the packet should be forwarded. The addresses in the previous slide all use the "link-local" scope (FF02), which stays in the local subnet.
IPv6 multicast scopes:
- Interface-local (FF01): The packet doesn't leave the local device. Can be used to send traffic to a service within the local device.
- Link-local (FF02): The packet remains in the local subnet. Routers will not route the packet between subnets. 
- Site-local (FF05): The packet can be forwarded by routers. Should be limited to a single physical location (not forwarded over a WAN)
- Organization-local (FF08): Wider in scope than site-local (an entire company/organization).
- Global (FF0E): No boundaries. Possible to be routed over the Internet.
![](/images/multicast%20address%20scopes.png)

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

![](/images/ipconfigall.png)


## 1.11 Describe wireless principles
Wireless network have some issues that need to be dealt with.

1. All devices within range receive all frames, like devices connected to an Ethernet hub.
- Privacy of data within the LAN is a greater concern.
- CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance) is used to facilitate half-duplex communications.
2. Wireless communications are regulated by various international and national bodies.
3. Wireless signal coverage area must be considered.
- Signal range, absorption, reflection, refraction, diffraction, and scattering.
4. Other devices using the same channels can cause interference.
- For example, a wireless LAN in your neighbor's house/apartment.


### 1.11.a Nonoverlapping Wi-Fi channels

In a small wireless LAN with only a single AP (Access Point), you can use any channel.

However, in larger WLANs with multiple APs, it's important that adjacent APs don't use overlapping channels. This helps avoid interference.

In the 2.4 GHz band, it is recommended to use channels 1, 6, and 11.
Using channels 1,6 and 11, you can place AP's in a 'honeycomb' pattern to provide complete coverage of an area without interference between channels.
![](/images/honeycomb.png)

### 1.11.b SSID
802.11 defines different kinds of service sets which are groups of wireless network devices. 

There are three main types:
- Independent
    - An IBSS (Independent Basic Service Set) is a wireless network in which two or more wireless devices connect directly without using an AP (Access Point)
    - Also called an ad hoc network
    - Can be used for file transfer (ie. Airdrop)
    - Not scalable beyond a few devices
- Infrastructure
    - A BSS (Basic Service Set) is a kind of Infrastructure Service Set in which clients connect to each other via an AP (Access Point), but not directly to each other.
    - A BSSID (Basic Service Set ID) is used to uniquely identify the AP. 
        - Other APs can use the same SSID, but not the same BSSID
        - The BSSID is the MAC address of the AP's radio
    - Wireless devices request associate with the BSS.
    - Wireless devices that have asociated with the BSS are called 'cients' or 'stations'.
    - The area around an AP where its signal is usable is called a BSA (Basic Service Area)
    - Clients must communicate via the AP, not directly with each other.

![](/images/BSSnetwork.png)

- To create large wireless LANs beyond the range of a single AP, we use an ESS (Extended Service Set).
- APs with their own BSSs are connected by a wired network.
    - Each BSS uses the same SSID.
    - Each BSS has a unique BSSID.
    - Each BSS uses a different channel to avoid interference.
- Clients can pass between APs without having to reconnect, providing a seamless Wi-Fi experience when moving between APs.
    - This is called roaming.
- The BSAS should overlap about 10-15%.

![](/images/ESS.png)



- Mesh
    - An MBSS (Mesh Basic Service Set) can be used in situations where it's difficult to run an Ethernet connection to every AP.
    - Mesh APs use two radios: one to provide a BSS to wireless clients, and one to form a 'backhaul network' which is used to bridge traffic from AP to AP.
    - At least one AP is connected to the wired network, and it is called the RAP (Root Access Point)
    - A protocol is used to determine the best path through the mesh (similar to how dynamic routing protocols are used to determine the best path to a destination.

![](/images/MBSS.png)

All devices in a service set share the same SSID (service set identifier)
The SSID is a human-readable name which identifies the service set. (spaghetti and meatballs)
The SSID does NOT have to be unique.

![](/images/SSIDreview.png)

### 1.11.c RF
Wi-Fi uses two main bands (frequency ranges).
- 2.4 GHz band
    - The actual range is 2.400 GHz to 2.4835 GHz
- 5 GHz band
    - The actual range is from 5.150 GHz to 5.825 GHz
    - Divided into four smaller bands:
        - 5.150 GHz to 5.250 GHz
        - 5.250 GHz to 5.350 GHz
        - 5.470 GHz to 5.725 GHz
        - 5.725 GHz to 5.825 GHz

The 2.4 GHz band typically provides further reach in open space and better penetration of obstacles such as walls.
- However, more devices tend to use the 2.4 GHz band so interference can be a bigger problem compared to the 5 GHz band.

Each band is divided up into multiple 'channels'.
- Devices are configured to transmit and receive traffic on one (or more) of these channels.
The 2.4 GHz band is divided into several channels, each with a 22 MHz range.

![](/images/80211standards.png)


### 1.11.d Encryption
Although security is important in all networks, it is even more essential in wireless networks.
Because wireless signals are not contained within a wire, any device within range of the signal can receive the traffic.
In wire networks traffic is often only encrypted when sent over an untrusted network such as the Internet.
In wireless networks, it is very important to encrypt traffic sent between the wireless clients and the AP.
There are many possible protocols that can be used to encrypt traffic.
All devices on the WLAN will use the same protocol, however each client will use a unique encryption/decryption key so that other device can't read its traffic.
A 'group key' is used by the AP to encrypt traffic that it wants to send to all of tis clients.
- All of the clients associated with the AP keep that key so they can decrypt the traffic.
A MIC (Message Integrity Check) is added to messages to help protect their integrity.

Authentication methods:
- Open Authentication
    - The client sends an authentication request, and the AP accepts it. No questions asked.
    - This is clearly not a secure authentication method
    - After the client is authenticated and associated with teh AP, it's possible to require the user to authenticate via other methods before access to the network is granted (ie. Starbucks Wifi)
- WEP (Wired Equivalent Privacy)
    - WEP is used to provide both authenticatio and encryption of wireless traffic.
    - For encryption, WEP uses the RC4 algorithm.
    - WEP keys can be 40 bits or 104 bits in length
    - The above keys are combined with a 24-bit 'IV' (Initialization Vector) to bring the total length to 64 bits or 128 Benefits
    - WEP encryption is not secure and can easily be cracked.
    - WEP can be used for authentication like this:

![](/images/WEP.png)

- EAP (Extensible Authentication Protocol)
    - EAP is an authentication framework.
    - It defines a standard set of authentication functions that are used by various EAP Methods.
    - we will look at four EAP methods: LEAP, EAP-FAST, PEAP, and EAP-TLS.
    - EAP is integrated with 802.1X, which provide port-based network access control.

![](/images/EAP.png)

- LEAP (Lightweight EAP)
    - LEAP was developed by Cisco as an improvement over WEP.
    - Clients must provide a username and password to authenticate.
    - In addition, mutua authentication is provided by both the client and server sending a challenge phrase to each other.
    - Dynamic WEP keys are used, meaning that the WEP keys are changed frequently.
    - Like WEP, LEAP is considered vulnerable and should not be used anymore.

![](/images/LEAP.png)

- EAP-FAST (EAP Flexible Authenticaiton via Secure Tunneling)
    - EAP-FAST was also developed by Cisco.
    - Consists of three phrases
        - A PAC (Protected Access Credential) is generated and passed from the server to the client.
        - A secure TLS tunnel is established between the client and authentication server.
        - Inside of the secure (encrypted) TLS tunnel, the client and server communicate further to authenticate/authorize the client.

![](/images/EAPfast.png)

- PEAP (Protected EAP)
    - Like EAP-FAST, PEAP involves establsihing a secure TLS tunnel between the client and server.
    - Instead of a PAC, the server has a digital certificate.
    - The client uses this digital certificate to authenticate the server
    - The certificate is also used to estalbish a TLS tunnel
    - Because only the server provides a certificate for authentication, the client must still be authenticated within the secure tunnel, for example by using MS-CHAP (Microsfot Challenge-Handshake Authentication Protocol)

![](/images/PEAP.png)

- EAP-TLS (EAP Transport Layer Security)
    - Whereas PEAP only requires the AS to have a certificate, EAP-TLS requires a certificate on the AS and on every single client.
    - EAP-TLS Is the most secure wireless authentication method, but it is more difficult to implement than PEAP because every client device needs a certificate.
    - Because the client and server authenticate each other with digital certificates, there is no need to authenticate the client within the TLS tunnel.
    - The TLS tunnel is still used to exchange encryption key information 

![](/images/EAP-TLS.png)

Encryption and Integrity methods:
- TKIP (Temporal Key Integrity Protocol)
    - Based on WEP, but more secure
    - Should not be usde in modern networks
    - used in WPA
- CCMP (Counter/CBC-MAC Protocol)
    - CCMP was developed after TKIP and is more secure.
    - AES (Advanced Encryption Standard) counter mode for encryption
        - AES is the most secure encryption protocol currently available. It is used widely used all over the world.
        - There are multipel modes of operation for AES. CCMP uses 'counter mode'.
    - CBC-MAC for MIC to ensure integrity of messages
    - used in WPA2
- GCMP (Galois/Counter Mode Protocol)
    - GCMP is more secure and efficient that CCMP.
    - increased efficiency allows higher data throughput than CCMP.
    - GCMP consists of two algorithms:
        - AES counter mode for encryption
        - GMAC (Galois Message Authentication Code) for MIC to ensure the integrity of messages
    - used in WPA3

## 1.12 Explain virtualization fundamenetals (server virtualization, containers, and VRFs)
Before virtualization, there was a one-to-one relationship between a physical server and an operating system.
In that operating system, apps providing services such as a web server, email server, etc. would run.
One physical server would be used for the web server, one for the email server, one for the database server, etc.
This is inefficient for multiple reasons:
- Each physical server is expensive and takes up sapce, power, etc.
- The resources on each physical server (CPU, RAM, storage, NIC) are typically under-used.

![](/images/serverbeforevirtualization.png)

Type 1 Hypervisor
- Virtualization allows us to break the one-to-one relationship of hardware to OS, allowing multiple OS's to run on a single physical server.
- Each instance is called a VM (Virtual Machine)
- A hypervisor is used to manage and allocate the hardware resources (CPU, RAM, etc) to each VM.
- Another name for a hypervisor is VMM (Virtual Machine Monitor)
- The type of hypervisor which runs directly on top of the hardware is called a Type 1 hypervisor.
    - Examples include VMware ESXi, Microsoft Hyper-V, etc.
- Type 1 hypervisors are also called bare-metal hypervisors because they run directly on the hardware (metal).
    - Another term is native hypervisor
- This is the type of hypervisor used in data center environments. 

![](/images/type1hypervisor.png)

Type 2 Hypervisor
- Type 2 hypervisors run as a program on an operating system like a regular computer program.
    - Examples include VMware Workstation, Oracle VirtualBox, etc.
- The OS running directly on the hardware is called the Host OS, and the OS running in a VM is called a Guest OS.
- Another name for a Type 2 hypervisor is hosted hypervisor.
- Although Type 2 hypervisors are rarely used in data center environments, they are common on personal-use devices (for example, if a Mac/Linux user needs to run an app that is only support on Windows, or vice versa)

![](/images/type2hypervisor.png)

Benefits of Virtualization:
- Partitioning
    - Run multiple operating systems on one physical machine
    - Divide system resources between virtual machines
- Isolation
    - Provide fault and security isolation at the hardware level
    - Preserve performance with advanced resource controls
- Encapsulation
    - Save the entire state of a virtual machine to files
    - Move and copy virtual machines as easily as moving and copying files 
- Hardware Independence
    - Provision or migrate any virtual machine to any physical server

VMs are connected to each other and the external network via a virtual switch running on the hypervisor. Just like a regular physical switch, the vSwitch's interfaces can operate as access or trunk ports and use VLANs to separate the VMs at Layer 2. Interfaces on the vSwitch connect to the physical NIC (or NICs) of the server to communicate with the external network.

![](/images/VMnetwork.png)

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

>show vlan brief

![](/images/vlanconfig.png)

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
  
![](/images/ip%20phones/%20voice%20VLAN.png)


### 2.1.b Default VLAN

VLAN 1 is the default VLAN.
VLANs 1002-1005 exist by default and cannot be deleted.

### 2.1.c Connectivity


## 2.2 Configure and verify interswitch connectivity
Trunk ports = "tagged" ports
Access ports = "untagged" ports

DTP (Dynamic Trunking Protocol)
- Cisco proprietary protocol that allows Cisco switches to dyniamically determine their interface status (access or trunk) without manual configuration. For security purposes, manual configuration is reconmmended and DTP should be disabled on all switchports.
VTP (VLAN Trunking Protocol)
- allows you to configure VLANs on a central VTP server switch, and other switches (VTP clients) will synchronize their VLAN database to the server. It is designed for large networks with many VLANs, but is rarely used and not recommended.

### 2.2.a Trunk ports
Trunk ports can be used to carry from multiple VLANs over a single interface. Switches will "tag" all frames that they send over a trunk link. This allows the reciving switch to know which VLAN the frame belongs to.

>show interfaces trunk

![](/images/trunkconfig.png)

### 2.2.b 802.1q
802.1q is an industry standard trunking protocol.

The 802.1q tag is inserted between the Source and Type/Length fields of the Ethernet frame.
The tag is 4 bytes (32 bits) in length and consists of two main fields: TPID (Tag Protocol Identifier) and TCI (Tag Control Information).
The TPID is 2 bytes in length and is always set to a value of 0x8100, indicating the frame is 802.1q tagged
The TCI consists of 3 smaller fields:
- PCP (Priority Code Point), 3 bits
    - used for CoS (Class of Service), which prioritizes important traffic in congested networks.

![](/images/PCP/CoS.png)

- DEI (Drop Eligiblle Indicator), 1 bit
    - used to indicated frames that can be dropped if the network is congested 
- VID (VLAD ID), 12 bits
    - identifies the VLAN the frame belongs to. 

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
- It is enabled on Cisco devices (routers, switches, firewalls, IP phones, etc) by default.
- CDP messages are periodically sent to multicast MAC address 0100.0CCC.CCCC.
- When a device receives a CDP message, it processes and discards the message. It does NOT forward it to other devices.
- By default, CDP messages are sent once every 60 seconds. By default, the CDP holdtime is 180 seconds. If a message isn't received from a neighbor for 180 seconds, the neighbor is removed from the CDP neighbor table. 
- CDPv2 messages are sent by default.

![](/images/CDP%20config%20commands.png)
![](/images/CDP%20commands.png)


LLDP (Link Layer Discovery Protocol)
- LLDP is an industry standard protocol (IEEE 802.1AB)
- It is usually disabled on Cisco devices by default, so it must be manually enabled.
- A device can run CDP and LLDP at the same time.
- LLDP messages are periodically sent to multicast MAC address 0180.C200.000E.
- When a device receives an LLDP message, it processes and discards the message. It does NOT forward it to other devices.
- By default, LLDP messages are sent once every 30 seconds. By default, the LLDP holdtime is 120 seconds.
- LLDP has an additional timer called the "reinitialization delay". If LLDP is enabled (globally or on an interface), this timer will delay the actual initialization of LLDP. 2 seconds by default. 

![](/images/LLDPconfigcommands.png)
![](/images/LLDPcommands.png)


## 2.4 Configure and verify (Layer 2/Layer 3) EtherChannel (LACP)
When the bandwidth of the interfaces connected to end hosts is greater than the bandwidth of the connection to the distribution switch(es), this is called oversubscription, which can cause congestion.
EtherChannel groups multiple interfaces together to act as a single interface. STP will treat this group as a single interface.
EtherChannel is also known as Port Channel, or LAG (Link Aggregation Group)
EtherChannel load balances based on "flows". A flow is a communication between two nodes in the network. Frames in the same flow will be forwarded using the same physical interface.
The inputs used in the interface selection calculation can be configured
- inputs that can be used:
    1. Source MAC
    2. Destination MAC
    3. Source AND Destination MAC
    4. Source IP
    5. Destination IP
    6. Source and Destination IP




There are three methods of EtherChannel configuration on Cisco switches:
1. LACP (Link Aggregation Control Protocol), 802.3ad 
    - Dynamically negoties the creation/maintenance of the the EtherChannel (similary to DTP for trunks)

![](/images/LACPconfig.png)

2. PAgP (Port Aggregation Protocol)
    - Cisco propretary protocol
    - Dynamically negotiates the creation/maintenance of the EtherChannel.

3. Static EtherChannel
    - A protocol isn't used to determine if an EtherChannel should be formed. 
    - Interfaces are statically configured to form an EtherChannel.

![](/images/staticetherchannelconfig.png)

Up to 8 interfaces can be formed into a single EtherChannel (LACP allows up to 16, but only 8 will be active, the other 8 will be in standby mode, waiting for an active interface to fail.)

![](/images/showetherchannelsummary.png)
![](/images/showetherchannelportchannel.png)
![](/images/layer3etherchannel.png)
![](/images/etherchannelcommands.png)

## 2.5 Interpret basic operations of Rapid PVST+ Spanning Tree Protocol
STP (Spanning Tree Protocol) prevents Layer 2 loops by placing redundant ports in a blocking state, essentially disabling the interface.
These interfaces act as backups that can enter a forwarding state if an active (=currently forwarding) interface fails.
Interfaces in a blocking state only send or receive STP messages (called BPDUs = Bridge Protocol Data Units)
Cisco switches use a version of STP called PVST+ (Per-VLAN Spanning Tree), which runs a seperate STP 'instance' in each VLAN, so in each VLAN different interfaces can be forwarding/blocking. This allows for load balancing by blocking different ports in each VLAN.
Rapid PVST+ allows for much faster converging/adapting to network changes, similar to 802.1w (Rapid Spanning Tree Protocol).
>show spanning-tree

![](/images/spanning%20tree%20protocol.png)
![](/images/spanning%20tree%20port%20states.png)
![](/images/spanning%20tree%20timers.png)
![](/images/rapid%20spanning%20tree%20port%20states.png)

### 2.5.a Root port, root bridge (primary/secondary), and other port names
Switches use one field in the STP BPDU, the Bridge ID field, to elect a root bridge for the network.
The switch with the lowest Bridge ID becomes the root bridge. the default bridge priority is 32768 on all switches, so by default the MAC address is used as the tie-breaker (lowest MAC address becomes the root bridge). All ports on the root bridge are designated ports. Ports across from the root port are always designated ports. 
Each remaining switch will select ONE of its interfaces to be its root port. 
Root port selection:
1. Lowest root constructrs
2. Lowest neighbor bridge ID
3. Lowest neighbor port ID.

Each remaining collisions Domain will select ONE interface to be a designated port (forwarding state). The other port in the collision domain will be non-desingated (blocking).
- Designated port selection:
1. Interface on switch with the lowest root cost
2. Interface on switch with the lowest bridge ID
In RSTP, the non-designated port is split into two seperate roles:
- the alternate port role (blocking)
- the backup port role (two interfaces on same collision domain, via a hub)


spanning-tree vlan 10 root primary/secondary
- root primary = STP priority 24576
- root secondary = STP priority 28672

### 2.5.b Port states (forwarding/blocking)
Root/Designated ports remain stable in a Forwarding state.
Non-designated ports remain stable in a Blocking state. Interfaces in a Blocking state are effectively disabled to prevent loops.
Listening and Learning are transitional states which are passed through when an interface is activated, or when a Blocking port must transition to a Forwarding state due to a change in the network topology.

### 2.5.c PortFast
Spanning tree timer picture

Portfast allows a port to move immediately to the Forwarding state, bypassing Listening and Learning. If used, it must be enabled only on ports connected to end hosts. If enabled on a port connected to another switch it could cause a Layer 2 loop.

BPDU guard is another optional STP feature
- can be used to prevent an access port from participating in the spanning tree.
SW1(config-if)#spanning-tree portfast (default)

## 2.6 Describe Cisco Wireless Architectures and AP modes

## 2.7 Describe physical infrastructure connections of WLAN components (AP, WLC, access/trunk ports, and LAG)
- WLC ports are the physical ports that cables connect to.
- WLC interfaces are the logical interfaces within the WLC (ie. SVIs on a switch).
- WLCs have a few different kinds of ports:
    - Service port: A dedicated management port. Used for out-of-band management. Must connect to a switch access port because it only supports one VLAN. This port can be used to connect to the device while it is botting, perform system recovery, etc.
    - Distribution system port: These are the standard network ports that connect to the 'distribution system' (wired network) 
    - Console port: This is a standard console port, either RJ45 or USB.
    - Redundancy port: This port is used to connect to another WLC to form a high availability (HA) pair.

WLCs have a few different kinds of interfaces:
- Management interface: Used for management traffic such as Telnet, SSH, HTTP, HTTPS, RADIUS authentication, NTP, Syslog, etc. CAPWAP tunnels are also formed to/from the WLC's management interface.
- Redundancy management interface: When two WLCs are connected by their redundancy ports, one WLC is 'active' and the other is 'standby'. This interface can be used to connect to and manage the 'standby' WLC.
- Virtual interface: This interface is used when communicating with wireless clients to relay DHCP requests, perform client web authentication, etc.
- Sevice port interface: If the service port is used, this interface is bound to it and used for out-of-band management.
- Dynamic interface: These are the interfaces used to map a WLAN to a VLAN. For example, traffic from the 'Internal' WLAN will be sent to the wired network from the WLC's 'Internal' dynamic interface.

## 2.8 Describe AP and WLC management access connections (Telnet, SSH, HTTP, HTTPS, console, and TACACS+/RADIUS)
WLC config:
![](/images/WLC%20config.png)
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

![](/images/administrativedistance.png)

### 3.1.f Metric
A router's route table contains the best route to each destination network it knows about.
If a router using a dynamic routing protocol learns two different routes to the same destination, how does it determine which is 'best'?
It uses the metric value of the routes to dtermine which is best. A lower metric = better.
Each routing protocol uses a different metric to determine which route is best.
If a router learns two (or more) routes via the same routing protocol to the same destination (same network address, same subnet mask) with the same metric, both will be added to the routing table. Traffic will be load-balanced over both routes.
ECMP (Equal Cost Multi-Path)

![](/images/dynamicroutingmetrics.png)

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
A connected network route is automatically added for each connected network. 
A local host route is automatically added for each address configured on the router.
Routes for link-local addresses are not added to the routing table.
![](/images/localconnectedstaticinternalroutes.png)
![](/images/configstaticroute.png)
![](/images/ipv6%20static%20routing.png)
![](/images/ipv6%20static%20routing%20examples.png)




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

OSPF areas
- An area is a set of routers and links that share the same LSDB
- The backbone area (area 0) is an area that all other areas must connect to.
- Routers with all interfaces in the same area area called internal routers.
- Routers with interfaces in multiple areas are called area border routers (ABRs).
- Routers connected to the backbone area (area 0) are called backbone routers.
- An intra-area route is a route to a destination inside the same OSPF area.
- An interarea route is a route to a destination in a different OSPF area. 
- OSPF areas should be contiguous.
- All OSPF areas must have at least one ABR connected to the backbone area.
- OSPF interfaces in the same subnet must be in the same area.

![](/images/OSPF%20config.png)
![](/images/OSPF%20config%202.png)

![](/images/OSPF%20cost.png)
![](/images/OSPF%20cost%202.png)
![](/images/OSPF%20cost%203.png)

### 3.4.a Neighbor adjacencies
In OSPF, there are three main steps in the process of sharing LSAs and determining the best route to each destination in the network.
1. Become neighbors with other routers connected to the same segment
2. Exchange LSAs with neighbor routers
3. Calculate the best routes to each destination, and insert them into the routing table

![](/images/OSPF%20neighbors.png)
![](/images/OSPF%20exchanges.png)

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

![](/images/OSPF%20broadcast%20network%20type.png)
![](/images/config%20OSPF%20network%20type.png)

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
   
![](/images/FHRPcomparisons.png)

## 4.0 IP Services


## 4.1 Configure and verify inside source NAT using static and pools
NAT (Network Address Translation) is used to modify the source and/or destination IP addresses of packets. 
There are various reasons to use NAT, but the most common reason is to allow hosts with private IP addresses to communicate with other hosts over the Internet.
Static NAT involves statically configuring one-to-one mappings of private IP addresses to public IP addresses.  When traffic from the internal host is sent to the outside network, the router will translate the source address. However, this one-to-one mapping also allows external hosts to access the internal host via the inside global address.

An inside local IP address is mapped to an inside global IP address.
- Inside Local: The IP address of the inside host, from the perspective of the local network. (The IP address actually configured on the inside host, usually a private address)
- Inside Global: The IP address of the inside host, from the perspective of outside hosts (the IP address of the inside host after NAT, usually a public address)
![](/images/static%20NAT%20flowchart.png)

![](/images/static%20NAT%20config.png)

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

![](/images/dynamic%20NAT%20config.png)

Nat commands:
![](/images/show%20ip%20nat%20translations.png)
![](/images/NAT%20commands.png)
## 4.2 Configure and verify NTP operating in a client and server mode
NTP (Network Time Protocol) allows automatic syncing of time over a network. 
- NTP clients request the time from NTP servers.
- A device can be an NTP server and an NTP client at the same time.
- NTP allows accuracy of time within ~1 millisecond if the NTP server is in the same LAN, or within ~50 milliseconds if connecting to the NTP server over a WAN/the Internet.
- Some NTP servers are 'better' than others. The 'distance' of an NTP server from the orginal reference clock is called stratum.
- Reference clock is usually a very accurate time device like an atomic clock or a GPS clock.
- Reference clocks are stratum 0 within the NTP hierarchy. NTP servers directly connected to reference clocks are stratum 1 (primary servers). NTP servers that get their time from stratum 1 NTP servers are stratum 2 (secondary servers). 
- Stratum 15 is the maximum.
- An NTP client can sync to multiple NTP servers.
- Devices can also 'peer' with devices at the same stratum to provide more accurate time. This is called 'symmetric active' mode.
- Cisco devices can operate in three NTP modes:
    - Server mode
    - Client mode
    - Symmetric active mode
- NTP uses UDP port 123 to communicate.
- NTP uses only the UTC time zone. You must configure the appropriate time zone on each device.

![](/images/manual%20time%20config.png)
![](/images/NTP%20config.png)
![](/images/ntp%20authentication.png)
![](/images/NTP%20commands.png)
## 4.3 Explain the role of DHCP and DNS within the network
DNS (Domain Name System) is used to resolve human-readable names (google.com) to IP addresses.
When you type 'youtube.com' into a web browser, your device will ask a DNS server for the IP address of youtube.com.
The DNS server(s) your device uses can be manually configured or learned via DHCP.
Standard DNS queries/responses typically use UDP. TCP is used for DNS messages greater than 512 bytes. In either case, port 53 is used.
Devices will save the DNS server's responses to a local DNS cache. This means they don't have to query the server every single time they want to access a particular destination. 
>ipconfig /displaydns
>nslookup youtube.com

![](/images/DNSios.png)
![](/images/DNScommands.png)

DHCP (Dynamic Host Configuration Protocol)
- DHCP is used to allow hosts to automatically/dynamically learn various aspects of their network configuration, such as IP address, subnet mask, default gateway, DNS server, etc, without manual/static configuration.
- It is an essential part of modern networks. Typically used for 'client devices' such as workstations (PCs), phones, etc.
- Devices such as routers, servers, etc, are usually manually configured. 
- In small networks (such as home networks) the router typically acts as the DHCP server for hosts in the LAN. 
- In larger networks, the DHCP server is usually a Windows/Linux server.

![](/images/DHCPdora.png)


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

![](/images/SNMP%20messages.png)
![](/images/SNMPv2c%20config.png)
![](/images/SNMP%20summary.png)


## 4.5 Describe the use of syslog features including facilities and levels
Syslog is an industry standard protocol for message logging.
On network devices, Syslog can be used to log events such as changes in interface status (up<->down), changes in OSPF neighbor status, system restarsts, etc.
The messages can be displayed in the CLI, saved in the device's RAM, or sent to an external Syslog server.
Logs are essential when troubleshooting issues, examining the cause of incidents, etc.
Syslog and SNMP are both used for monitoring and troubleshooting of devices. They are complementary, but their functionalities are different.
![](/images/syslogmessageformat.png)
![](/images/syslogmessageexamples.png)
![](/images/syslogseveritylevels.png)
![](/images/syslog%20config.png)
![](/images/syslogcommandsummary.png)

![](/images/syslog%20vs%20SNMP.png)


## 4.6 Configure and verify DHCP client and relay
![](/images/DHCP%20server%20config.png)
![](/images/DHCPcommands.png)

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




## 4.8 Configure network devices for remote access using SSH
SSH (Secure Shell) allows for remote access while providing security features such as  data encryption and authentication. 
The SSH server (the device being connected to) listens for SSH traffic on TCP port 22.
To enable and use SSH, you must generate an RSA public and private key pair. The keys are used for data encryption/decryption, authentication, etc.
![](/images/SSH%20config-rsa.png)
![](/images/ssh%20config%20vty.png)

![](/images/ssh%20config.png)
![](/images/ssh%20config%20commands.png)

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

![](/images/FTP%20control%20connections.png)

TFTP is named trivial because it is simple and has only basic features compared to FTP. 
- Only allows a client to copy a file to or from a server.
- Released after FTP, but not a replacement for FTP. It is another tool to use when lightweight simplicity is more important than functionality.
- No authentication, servers will respond to all TFTP requests. No encryption, so all data is sent in plain text.
- Best used in a controlled environment to transfer small files quickly.
- TFTP servers listen on UDP port 69.
- UDP is connectionless and doesn't provide reliability with retransmissions, however, TFTP has similar built-in features within the protocol itself.
- TFTP uses 'lock-step' communication. The client and server alternately send a message and then wait for a reply. (+retransmissions are sent as needed)

![](/images/TFTP%20connections.png)

![](/images/FTPvsTFTP.png)
![](/images/FTPcommands.png)

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

![](/images/common%20security%20attacks.png)

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
To provide secure communications over the Internet, VPNs (Virtual Private Networks) are used. We will cover two kinds of Internet VPNs:
1. Site-to-Site VPNs using IPsec
2. Remote-access VPNs using TLS

Site-to-Site VPNs (IPsec)
- A site-to-site VPN is a VPN between two devices and is used to connect two sites together over the Internet.
- A VPN 'tunnel' is created between the two devices by encapsulating the original IP packet with a VPN header and a new IP header.
    - When usuing IP sec, the original packet is encrypted before being encapsulated with the new header.
Site-to-site VPNs:

![](/images/Site-to-Site%20VPNs%20(IPsec).png)
![](/images/ipsec.png)

There are some limitations to standard IPsec:
1. IPsec doesn't support broadcast and multicast traffic, only unicast. This means that routing protocols such as OSPF can't be used over the tunnels, because they rely on multicast traffic.
    - This can be solved with 'GRE over IPsec'
    - GRE (Generic Routing Encapsulation) creates tunnels like IPsec, however it does not encrypt the original packet, so it is not secure.
    - However, it has the advantage of being able to encapsulate a wide variety of Layer 3 protocols as well as broadcast and multicast messages.
    - To get the flexibility of GRE with the security of IPsec, 'GRE over IPsec' can be used.
    - The original packet will be encapsulated by a GRE header and a new IP header, and then the GRE packet will be encrypted and encapsulated within an IPsec VPN header and new IP header.

![](/images/GREoverIPsec.png)

2. Configuring a full mesh of tunnels between many sites is a labor-intesive task.
    - This can be solved with Cisco's DMVPN.
    - DMVPN (Dynamic Multipoint VPN) is a Cisco-developed solution that allows routers to dynamically create a full mesh of IPsec tunnels without having to manually configure every single tunnel.
    - DMVPN provides the configuration simplicity of hub-and-spoke (each spoke router only needs one tunnel configured) and the efficiency of direct spoke-to-spoke communication (spoke routers can communicate directly without traffic passing through the hub)

![](/images/DMVPN.png)

Remote-Access VPNs 
- Whereas site-to-site VPNs are used to make a point-to-point connection between two sites over the Internet, remote-access VPNs are used to allow end devices (PC, mobile phones) to access the company's internal resources securely over the Internet.
- Remote-access VPNs typically use TLS (Transport Layer Security)
    - TLS is also what provides security for HTTPS (HTTP Secure)
    - TLS was formerly known as SSL (Secure Sockets Layer) and developed by Netscape, but was renamed to TLS when it was standardized by the IETF.

- VPN client software (for example Cisco AnyConnect) is installed on en end devices (for example company-provided laptops that employees work from home).
- These end devices then form secure tunnels to one of the company's router/firewalls acting as a TLS server.
- This allows the end users to securely access resources on the company's internal network without being directly connected to the company network.
Remote-Access VPNS:
![](/images/remote-access%20VPNs.png)
![](/images/remote-accessvpnnetwork.png)

Site-to-Site vs Remote-Access VPN
- Site-to-Site VPNs typically use IPsec.
- Remote-Access VPNs typically use TLS.

- Site-to-Site VPNs provide service to many devices within the sites they are connecting.
- Remote-Access VPNs provide  service to the one end device the VPN client software is installed on.

- Site-to-Site VPNs are typically used to permanently connect two sites over the Internet.
- Remote-Access VPNs are typically used to provide on-demand access for end devices that want to securely access company resources while connected to a network which is not secure.


## 5.6 Configure and verify access control lists
ACLs (Access Control Lists) function as a packet filter, instructing the router to permit or discard specific traffic. 
ACLs can filter traffic based on source/destination IP addresses, source/destination IP addresses, source/destination Layer 4 ports, etc.
ACLs are configured globally on the router, and consist of an ordered sequence of ACEs (Access Control Entries)
Configuring an ACL will not make the ACL take effect, the ACL must be applied to an interface. ACLs are applied either inbound or outbound.
If the packet matches one of the ACEs in the ACL, the router takes the action and stops processing the ACL, all entries below the matching entry will be ignored. 
There is an implicit deny at the end of all ACLs. The implicit deny tells the router to deny all traffic that doesn't match any of the configured entries in the ACL.
Standard ACLs: Match based on the Source IP address only.
- Standard ACLs can use 1-99 and 1300-1999.
- Standard ACLs should be applied as close to the destination as possible.
- R1(config)# access-list (#) (deny/permit) (ip) (wildcard-mask)
    R1(config-if)# ip access-group (#) (in/out)
Extended ACLs: Match based on Source/Destination IP, Source/Destination port/protocol, etc
- Extended ACLs can use 100-199, 2000-2699.
- Extended ACLs should be appleid as close to the source as possible.
>R1(config)# access-list (#) (permit/deny) (protocol) (src-ip) (dest-ip)
>R1(config)# ip access-list extended (name/number)
>R1(config-ext-nacl)# (seq-num) (permit/deny) (protocol) (src-ip) (dest-ip)

![](/images/configuringnumberedACLs.png)
![](/images/namedACLadvantages.png)
![](/images/namedACLadvantages2.png)
![](/images/extendedACLprotocols.png)
![](/images/extendedACLexample.png)
![](/images/extendedACLtcpudp.png)



## 5.7 Configure and verify Layer 2 security features (DHCP snooping, dynamic ARP inspection, and port security)
DHCP snooping is security feature of switches that is used to filter DHCP messages received on untrusted ports.
DHCP snooping only filters DHCP messages. Non-DHCP messages aren't affected.
All ports are untrusted by default.
- Usually, uplink ports are configured as trusted ports, and downlink ports remain untrusted.
![](/images/DHCP%20snooping%20operations.png)
![](/images/DHCPsnooping.png)
![](/images/DHCPsnoopingcommands.png)



Dynamic ARP inspection (DAI) is a security feature of switches that is used to filter ARP messages received on untrusted ports.
DAI only filters ARP messages. Non-ARP messages aren't affected.
All ports are untrusted by default.
- Typically, all ports connected to other network devices (switches, routers) should be configured as trusted, while itnerfaces connected to end hosts should remain untrusted.

![](/images/DAIconfig.png)
![](/images/showiparp.png)
![](/images/dairatelimit.png)
![](/images/DAIcomands.png)

Port security is a security feature of Cisco switches. It allows you to control which source MAC address(es) are allowed to enter the switchport.
If an authorized source MAC address enters the port, an action will be taken.
- The default action is to place the interface in an 'err-disabled' state.
When you enable port security on an interface with the default settings, one MAC Addres is allowed.
- You can configure the allowed MAC address manually.
- If you don't configure it manually, the switch will allow the first source MAC address that enters the interface.
- You can change the maximum number of MAC addresses allowed
- A combination of manually configured MAC addresses and dynamically learned addresses is possible.

![](/images/config%20port%20security.png)
![](/images/verify%20port%20security.png)
![](/images/errdisable%20recovery.png)
![](/images/violation%20modes.png)
![](/images/portsecurity%20commands.png)

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
The Wi-Fi alliance has developed three WPA certifications for wireless devices:
- WPA
- WPA2
- WPA3

To be WPA-certified, equipment must be tested in authorized testing labs.
All of the above support two authentication modes:
- Personal mode: A pre-shared key (PSK) is used for authentication. When you connect to a home Wi-Fi network, enter the password and are authenticated, that is personal mode. This is common in small networks. The PSK itself is not sent over the air. A four-way handshake is used to generate encryption keys.
- Enterprise mode: 802.1X is used with an authentication server (RADIUS server).  *No specific EAP method is specified, so all are supported (PEAP, EAP-TLS, etc).

The WPA certification was developed after WEP was proved to be vulnerable and includes the following protocols:
- TKIP (based on WEP) provides encryption/MIC
- 802.1X authentication (Enterprise mode) or PSK (Personal mode)

WPA2 was released in 2004 and includes the following protocols:
- CCMP provides encryption/MIC.
- 802.1X authentication (Enterprise mode) or PSK (Personal mode)

WPA3 was released in 2018 and includes the following protocols:
- GCMP provides encryption/MIC
- 802.1X authentication (Enterprise mode) or PSK (Personal mode)
- WPA3 also provides serveral additional security features, for example:
    - PMF (Protected Management Frames), protecteing 802.11 management frames from eavesdropping/forging.
    - SAE (Simulataneous Authentication of Equals) protects the four-way handshake when using personal mode authentication.
    - Forward secrecy prevents data from being decrypted after it has been transmitted over the air, to prevent an attacker from capturing wireless frames and then trying to decrypt them later.

## 5.10 Configure and verify WLAN within the GUI using WPA2 PSK


## 6.0 Automation and Programmability
There are various tools/methods that can be used to automate tasks in the network:
- SDN (Software-Defined Networking)
- Ansible
- Puppet
- Python scripts, etc

## 6.1 Explain how automation impacts network management
Network automation provides many key benefits:
- Human error (typos etc.) is reduced.
- Network become much more scalable. New deployments, network-wide changes, and troubleshooting can be implemetned in a fraction of time.
- Network-wide policy compliance can be assured (standard configurations, software versions, etc).
- The improved efficiency of network operations reduces the opex (operating expenses) of the network. Each task requires fewer man-hours.

## 6.2 Compare traditional networks with controller-based networking
In traditional networking, the data plane and control plane are both distributed. Each device has its own data plane and its own control plane. The planes are 'distributed' throughout the network.
Networking tasks can be automated in tradition network architectures too:
- Scripts can be written (ie. using Python) to push commands to many devices at once
- Python with good use of Regular Expression can parse through show commands to gather infromation about the network devices.
However, the robust and centralized data collected by SDN controllers greatly facilitates these functions. 
- The controller collects information about all devices in the network.
- Northbound APIs allows apps to access information in a format that is easy for programs to understand (ie. JSON, XML)
- The centralized data facilitates network-wide analytics.

SDN tools can provide the benefits of automation without the requirement of third-party scripts & apps.
- You don't need expertise in automation to make use of SDN tools.
- However, APIs allow third-party applications to interact with the controller, which can be very powerful.

Although SDN and automation aren't the same thing, the SDN architecture greatly facilitates the automation of various tasks in the network via the SDN controller and APIs.

## 6.3 Describe controller-based, software defined architecture (overlay, underlay, and fabric)
SDN (Software-Defined Networking) is an approach to networking that centralizes the control plane into an application called a controller.
SDN is also called the Software-Defined Architecture (SDA) or Controller-Based Networking.
Traditional control planes use a distributed architecture.
- For example, each router in the network runs OSPF and the routers share routing information and then calculate their preferred routers to each destination.
An SDN controller centralizes control plane functions like calculating routes.
- That is just an example, and how much of the control plane is centralized varies greatly.
The controller can interact programmatically with the network devices using APIs (Application Programming Interface)
The SBI is used for communications between the controller and the network devices it controls.
The NBI is what allows us to interact with the controller with our scripts and applications.

![](/images/DNA%20center.png)


- The underlay is the underlying physical network of devices and connections (including wired and wireless) which provide IP connectivity (ie. using IS-IS).
    - Multilayer switches and their connections
- The overlay is the virtual network built on top of the physical underlay network.
    - SD-Access uses VXLAN (Virtual Extensible LAN) to build tunnels
- The fabric is the combination of the overlay and underlay; the physical and virtual network as a whole.

SD-Access Underlay
- The underlay's purpose is to support the VXLAN tunnels of the overlay.
- There are three different roles for switches in SD-Access:
    - Edge nodes: Connect to end hosts
    - Border nodes: Connect to devices outside of the SD-Access domain, ie. WAN routers
    - Control nodes: Use LISP (Locator ID Seperation Protocol) to perform various control plane functions.
- You can add SD-Access on top of an existing network (brownfield deployment) if your network hardware and software supports it.
    - Google 'Cisco SD-Access compatibility matrix' if you're curious.
    - In this case DNA Center won't configure the underlay.
- A new deployment (greenfield deployment) will be configured by DNA Center to use the optimal SD-Access underlay:
    - All switches are Layer 3 and use IS-IS as their routing protocol.
    - All links between switches are router ports. This means STP is not needed.
    - Edge nodes (access switches) act as the default gateway of end hosts (routed acces layer)

![](/images/Traditional%20LAN.png)
![](/images/SD-access%20underlay.png)



SD-Access Overlay
 LISP provides the control plane of SD-Access
 - A list of mappings of EID (endpoint identifiers) to RLOCs (routing locations) is kept.
 - EIDs identify end hosts connected to edge switches, and RLOCs identify the edge switch which can be used to reach the end host.
 - There is a LOT mroe detail to cover about LISP, but this is just to show how it differs form the traditional control plane.
 Cisco TrustSec (CTS) provides policy control (QoS, security policy, etc)
 VXLAN provides the data plane of SD-Access.   

![](/images/SD-access%20overlay.png)

### 6.3.a Seperation of control plane and data plane
The various functions of network devices can be logically divided up (categorized) into planes:
- Data plane
    - All tasks involved in forwarding user data/traffic from one interface to another are part of the data plane.
    - A router receives a message, looks for the most specific matching route in its routing table, and forwards it out of the appropriate interface to the next hop.
        - It also de-encapsulates the original Layer 2 header, and re-encapsulates with a new header destined for the next hop's MAC address.
    - A switch receives a message, looks at the destination MAC address, and forwards it out of the appropriate interface (or floods it).
        - This includes functions like adding or removing 802.1q VLAN tags.
    - NAT (changing the src/dst addresses before forewarding) is part of the data plane.
    - Deciding to forward or discard messages due to ACLs, port security, etc. is part of the data plane.
    - The data plane is also called the 'forwarding plane'.
- Control plane
    - How does a device's data plane make its forwarding decisions?
        - routing table, MAC address table, ARP table, STP, etc.
    - Functions that build these tables (and other functions that influence the data plane) are part of the control plane.
    - The control plane controls what the data plane does, for example by building the router's routing table.
    - The control plane performs overhead work.
        - OSPF itself doesn't forward user data packets, but it informs the data plane about how packets should be forwarded.
        - STP itself isn't directly involved in the process of forwarding frames, but it informs the data plane about which interfaces should and shouldn't be used to forward frames.
        - ARP messages aren't user data, but they are used to build an ARP table which is used in the process of forwarding data.
- Management plane
    - Like the control plane, the management plane performs overhead work.  
        - However, the management plane doesn't directly affect the forwarding of messages in the data plane.
    - The management plane consists of protocols that are used to manage devices.
        - SSH/Telnet, used to connect to the CLI of a device to configure/manage it.
        - Syslog, used to keep logs of events that occur on the device.
        - SNMP, used to monitor the operations of the device.
        - NTP, used to maintain accurate time on the device.

When a device received control/management traffic (destined for itself), it will be processed in the CPI.
When a device receives data traffic which should pass through the device, it is processed by the ASIC for maximum speed.

### 6.3.b Northbound and Southbound APIs
The SBI (Southbound Interface) is used for communications between the controller and the network devices it controls.
It typically consists of a communication protocol and API (Application Programming Interface)
APIs facilitate data exchanges between programs.
- Data is exchanged ibetween the controller and the network devices.
- An API on the network devices allows the controller to access information on the devices, control their data plane tables, etc
Some examples of SBI's are: OpenFlow, Cisco OpFlex, Cisco onePK (Open Network Environment Platform Kit), NETCONF
Using the SBI, the controller communicates with the managed devices and gathers information about them:
- The devices in the network
- The topology (how the devices are connected together)
- the available interfaces on each device
- their configurations

The NBI (Northbound Interface) is what allows us to interact with the controller, access the data it gathers about the network, program it, and make changes in the network via the SBI.
A REST (Representational State Transfer) API is used on the controller as an interface for apps to interact with it.

Data is sent in a structure (serialized) format such as JSON or XML.
- This makes it much easier for programs to use the data.

![](/images/networkautomation.png)



## 6.4 Compare traditional campus device management with Cisco DNA Center enabled device management
Cisco SD-Access is Cisco's SDN solution for automating campus LANs.
- ACI (Application Centric Infrastructure) is their SDN solution for automating data center networks.
- SD-WAN is their SDN solution for automating WANs
- Cisco DNA (Digital Network Architecture) Center is the controller at the center of SD-Access.
Cisco DNA Center has two main roles
- The SDN controller in SD-access
- A network manager in a traditional network (non-SD-Access)
- DNA Center is an application installed on Cisco UCS server hardware.
- It has a REST API which can be used to interact with DNA center.
- The SBI supports protocols such as NETCONF and RESTCONF (as well as traditional protocols like Telnet, SSH, SNMP)
- DNA Center enables Intent-Based Networking (IBN).
    - The goal is to allow the engineer to communicate their intent for network behavior to DNA Center, and then DNA Center will take care of the details of the actual configurations and policies on devices.



Traditional security policies using ACLs can become very cumbersome.
- ACLs can have thousands of entries.
- The intent of entries is forgotten with time and as engineers leave and new engineers take over.
- Configuring and applying the ACLs correctly across a network is cumbersome and leaves room for error.
- DNA Center allows the engineer to specify the internet of the policy (this group of users can't communicate with this grup, this group can access this server but not that server, etc) and DNA Center will take care of the exact details of implementing the policy.

Traditional network management:
- Devices are configured one-by-one via SSH or console connection
- Devices are manually configured via console connection before being deployed
- Configurations and policies are managed per-device (distributed)
- New network deployments can take a long time due to the manual labor required
- Errors and failures are more likely due to increased manual effort.
DNA Center-based network management:
- Devvices are centrally managed and monitored from the DNA Center GUI or other applications using its REST API.
- The administrator communicates their intended network behavior to DNA Center, which changes those intentions into configurations on the managed network deivces.
- Configurations and policies are centrally manaaged.
- Software versions are also centrally managed. DNA Center can monitor cloud servers for new versions and then update the manged devices.
- New network deployments are much quicker. New devices can automatically receive the configurations from DNA Center without manual configuration.

## 6.5 Describe characteristics of REST-based APIs (CRUD, HTTP verbs, and data encoding)
An API (Application Programming Interface) is a software interface that allows two applications to communicate with each other.
APIs are essential not just for network automation, but for all kinds of applications.
In SDN architecture, APIs are used to communicate between apps and the SDN controller (via the NBI), and between the SDN controller and the network devices (via the SBI).
The NBI typically uses REST APIs. NETCONF and RESTCONF are popular southbound APIs.
![](/images/SDN%20architecture.png)


CRUD (Create, Read, Update, Delete) refers to the operations we perform using REST APIs.
- Create operations are used to create new variables and set their intial values.
    - ie. create variable "ip_address" and set the value to "10.1.1.1"
- Read operations are used to retrieve the value of a variable.
    - ie. what is the value of variable "ip_address"?
- Update operations are used to change the value of a variable.
    - ie. change the value of variable "ip_address" to "10.2.3.4"
- Delete operations are used to delete variables.
    - ie. delete variable "ip_address"

HTTP uses verbs (aka. methods) that map to these CRUD operations.
REST APIs typically use HTTP.
When an HTTP client sends a request to an HTTP server, the HTTP header includes information like this.
- An HTTP Verb (ie. GET)
- A URI (Uniform Resource Identifier), indicating the resource it is trying to access.

![](/images/CRUD%20and%20HTTP%20verbs.png)
![](/images/HTTP%20request.png)
![](/images/HTTP%20response.png)
![](/images/HTTP%20response%202.png)

REST stands for Representational State Transfer.
REST APIs are also known as REST-based APIs or RESTful APIs.
- REST isn't a specific API. Instead, it describes a set of rules about how the API should work.

The six constraints of RESTful architectures are:
- Uniform Interface
- Client-server
- Stateless
- Cacheable or non-cacheable
- Layered system
- Code-on-demand (optional)

REST APIs must support caching of data.
Caching refers to storing data for future use.
- For example, your computer might cache many elements of a web page so that it doesn't have to retrieve the entire page every time you visit it.
- This improves performance for the client and reduces the load on the server
Not all resources have to be cacheable, but cacheable resources MUST be declared as cacheable.

## 6.6 Recognize the capabilities of configuration management mechanisms Puppet, Chef, and Ansible
Configuration management tools are network automation tools that facilitate the centralized control of large numbers of network devices.
These tools were originally developed after the rise of VMs, to enable server system admins to automate the process of creating, configuring, and removing VMs.
- However, they are also widely used to manage network devices.
These tools can be used to perform tasks such as:
- Generate configurations for new devices on a large scale.
- Perform configuration changes on devices (all devices in your network, or a certain subset of devices)
- Check device configurations for compliance with defined standards.
- Compare configurations between devices, and between different version of configurations on the same device.

Ansible is a configuration management tool owned by Red Hat.
- Ansible itself is written in Python
- Ansible is agentless
    - it doesn't require any special software to run on the managed devices
- Ansible uses SSH to connect to devices, make configuration changes, extract information, etc.
- Ansible uses SSH to connect to devices, make configuration changes, extract information, etc.
- Ansible uses a push mdoel. The ansible server (Control node) uses SSH to connect to managed devices and push configuration changes to them
    - Puppet and Chef use a pull model

![](/images/ansiblemodel.png)

- After installing Ansible itself, you must create several text files:
    - Playbooks
        - These are files are 'blueprints of automation tasks'. They outline the logic and actions of the tasks that Ansible should do. Written in YAML.
    - Inventory
        - These files list the devices that will be managed by Ansible, as well as characteristics of each device such as their device role (access switch, core switch, WAN router, firewall,etc). Written in INI, YAML, or other formats.  
    - Templates
        - These files represent a device's configuration file, but specific values for variables are not provided. Written in a Jinja2 format.
    - Variables
        - These files list variables and their values. These values are substituted into the templates to create complete configuration files. Written in YAML.

Puppet is a configuration mangement tool written in Ruby.
- Puppet is typically agent-based 
    - Specific software must be installed on the managed devices.
    - Not all Cisco devices support a Puppet agent.
- It can be run agentless, in which a proxy agent runs on an external host, and the proxy agent uses SSH to connect to the managed devices and communicate with them.
- The puppet server is called the 'Puppet master'.
- Puppet uses a pull model (clients 'pull' configurations from the Puppet master).
    - CLients use TCP 8140 to communicate with the Puppet master.
- Instead of YAML, it uses a proprietary language for files.
- Text files required on the Puppet master include:
    - Manifest: This file defines the desired configuration state of a network device.

![](/images/puppetmodel.png)

Chef is a configuration management tool written in Ruby.
- Chef is aagent-based
    - Specific software must be installed on the managed devices.
    - Not all Cisco devices support a Chef agent.
- Chef uses a pull model
- The server uses TCP 10002 to send configurations to clients
- Files use a DSL (Domain-Sepcific Language) based on Ruby.
- Text files used by Chef include:
    - Resources: The 'ingredients' in a recipe. Configuration objects managed by Chef.
    - Recipes: The 'recipes' in a cookbook. Outline the logic and actions of the tasks performed on the resources.
    - Cookbooks: A set of related recipes grouped together.

![](/images/chefmodel.png)

Ansible, Puppet, Chef comparison:
![](/images/ansiblepuppetchef.png)

## 67 Recognize components of JSON-encoded data
Data serialization is the process of converting data into standardized format/structure that can be stored (in a file) or transmitted (over a network) and recontructed later (ie. by a different application). 
- This allows the data to be communicated between applications in a way both applications understand.

- Data serialization languages allow us to represent variable with text.
![](/images/data%20serialization.png)


JSON (JavaScript Object Notation) is an open standard file format and data interchange format that uses human-readable text to store and transmit data objects.
It was derived from JavaScript, but it is languaage-independent and many modern programming languages are able to generate and read JSON data.
- REST APIs often use JSON.
Whitespace is insignificant.
JSON can represent four 'primitive' data types:
- string
- number
- boolean
- null
    - a null value represents the intentional absence of any object value. It is not surrounded by quotes.
![](/images/JSON%20example.png)

JSON also has two 'structured' data types:
- object
    - An object is an unordered list of key-value pairs (variables)
    - the key is a string
    - the value is any valid JSON data type (string, number, boolean, null, object, array)
    - The key and value are seperated by a colon.
    - If there are multiple key-value pairs, each pair is seperated by a comma.
![](/images/JSON%20object%20format.png)
    
- array
    - An array is a series of values seperated by commas.
    - not key-value pairs
    - the values don't have to be the same data type.
![](/images/JSON%20array%20format.png)

XML (Extensible Markup Language) was developed as a markup languaage, but is now used as a general data serialization language.
- markup languaages (ie. HTML) are used to format text (font, size, color headings, etc)
- Often used by REST APIs

YAML (YAML Ain't Markup Language) is named to distinguish its purpose as a data-serialization languaage rather than a markup language.
YAML is used by the network automation tool Ansible.
YAML is very human-readable.
Whitespace is significant (unlike JSON and XML)
- Indentation is very important

