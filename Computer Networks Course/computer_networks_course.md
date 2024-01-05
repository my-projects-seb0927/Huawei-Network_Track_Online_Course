# Huawei - Network Track Online Course

## Basics of Computer Network

**What is a computer network**
A computer network connects multiple computers through communication links to share resource and deliver information.

A computer network is a complex system that involves comprehensive technologies

**What is a protocol**

In order to achieve interconnection and interoperation, different system entities on the computer network must comply with mutually acceptable rules during communication. A set of these rules is called a **communication procedure** or **protocol**.

Protocols must be formulated or agreed upon in advance so that the communication parties can understand the meaning of each other's information

**Classification of computer networks**
This is how computer networks are classified:
- **Based on the Networking Sharing Service Mode:**
	- *Client/Server* (C/S) network
	- *Peer to Peer* (P2P) network
	- *Browser/Server* (B/S) network
	- *Hybrid Networks*
- **Based on Network Nodes' Distribution Ranges**
	- *Local area network (LAN)*: A computer network that spans a distance of no more than 10 km.
	- *Metropolitan area network (MAN)*: It typically spans a distance of 10 km to 100 km.
	- *Wide area network (WAN)*: It spans a distance of more than 1000 km. It's usually has interconnected LANs or MANs

The reason because computer networks are divided in different layers is because it is easier to understand, letting some advantages as:
- Facilitate layer-by-layer system analysis and resolver overarching problems
- Developing layer-specific standards makes it easier to understand and revise such standards.
- After layering, the system is easier to modify and maintain.
- Etc.

**What is the OSI Model**
The OSI model was created to establish an open Internet standard. This model divides the network structure into seven layers:
- *The application layer:* Provides interfaces between network services and end users
- *The presentation layer:* Provides functions such as data presentation, encryption/decryption, and compression/decompression.
- *The session layer:* Establishes, manages, and terminates sessions.
- *The transport layer:* Defines the protocol, port number for data transmission and provides functions of flow control and error detection.
- *The network layer:* Performs local addressing and implements route selection between different networks.
- *The data link layer:* Provides functions such as establishing logical connections, hardware addressing, and error connection.
- *The physical layer:* Establishes, maintains, and disconnects physical connections

The first three ones are grouped into the **Application Layer** and then we hace the *Five-layer Internet Reference Model*.

** What is Data Transition**
Data sending is achieved through a typical application data encapsulation process:
1. The user data is encapsulated with the application layer header through the application layer protocol, resulting in the application data.
2. The application data is encapsulated with a TCP header at the transport layer resulting in a packet **(Data segment)**.
3. The packet is transmitted to the network layer and encapsulated with an IP header **(Data Packet)**.
4. The encapsulated IP packet is transmitted to the data link layer which encapsulates it with a MAC header resulting in a **Data Frame** 
5. The Data Frame is transmitted to the Ethernet card **(Data transmission process)**

**How does Data Reception works**
It receives data unpacking data layer by layer starting from the Ethernet card. It's the process from above but in reverse.
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/eb867ec2-233e-48d3-a53e-b4c3e4c3754b)


****
## Core Protocols
**Computer network protocols**
In a computer network, various specifications or protocols must be used to ensure secure, stable, and efficient running of the network. These protocols include the following types:

- **Network node identification protocol**: It is used to identify network nodes. Some examples are MAC, IPv4, IPv6 and RFID.
- **Network data transmission protocol**: It is used to ensure that network node data reaches the target node correctly. It includes HDLC, TCP, and UDP.
- **Network link contention protocol**: It is used to ensure that each network node has an opportunity to transmit data using a network link. It includes CSMA and Token.
- **Network resource sharing protocol**: It is used to ensure that different organizations and individuals can share information. It includes HTTP, FTP, and SMTP.

**Network node identity protocol**
- A **LAN** uses a network hardware address or a MAC address to uniquely identify each network node.
- A **WAN** that is formed by multiple interconnected LANs use a logical address, or an IP address to uniquely identify each network node

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/8205de86-c3ca-4f9f-9ab6-6c896d825543)


**MAC address**
To ensure that each node in a LAN can be uniquely identified, the IEEE stipulates that each node must have a unique network label. That's the MAC address
> 💡 It is also called the LAN address, physical address, etc.

It is used to identify the identity or location of a network node. It's written into the hardware by a network device manufacturer during production. A MAC address is inside a NIC.

- A MAC address consists of 48 bits. 6 bytes that are each separated by "." or "-". *EX: 08-00-20-0A-8c-6D*
- A MAC address cannot be replaced (*Theoretically*) unless you replace the network adapter.
- The LAN uses MAC addresses to identify specific users.

> **How to identify the MAC address?**
> Control Panel > Network > Local Area Connection Status > Details.

**IP Address**
In order to shield the differences between LANs, and in order to implement interconnection and interworking between different physical networks. IP address is an addressing method for allocating a unique address to each host on each subnet on the Internet.

- An IP address consists of 32-bit binary number, which is usually divided into four bytes. *EX: 192.168.85.17*

They are classified into five types:
- **Class A, Class B, Class C, Class D and Class E**
- **Class D** are used for multicast
- **Class E** are reserved for future use
- Only the three first IP addresses can be allocated
- **Class A:** They are used in large-scale regional networks. It supports a maximum of 2^24 hosts
- **Class B:** They are used for large-scale organizations and companies. It supports a maximum of 65534 hosts.
- **Class C:**  They are used for small organizations and  companies. It supports a maximum of 254 hosts.
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/49dfbaca-78ec-4c48-aff1-a2a709d83ec4)

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/9a7ac743-ef88-4428-8d29-6e1d4a09981b)



> **There are some rules for IP addresses by the Network Information Center**
> - An IP address with all 32 bits is set to 1 is a broadcast address..
> - An IP address with all 32 bits set to 0 is the network itself.
> - The eight most significant bits are 01111111 indicating the loopback address, which is used for network software test and communication between local processes. The most common one is (127.0.0.1)

**Differences betwen IP address and MAC address**
|                       **IP address**                      |                       **MAC address**                       |
|:---------------------------------------------------------:|:-----------------------------------------------------------:|
|                     It can be changed                     |                     It cannot be changed                    |
|                      Length: 32 bits                      |                       Length: 48 bits                       |
| They are used at Layer 3 of the OSI model (Network layer) | They are used at Layer 2 of the OSI model (Data link layer) |

## Network Node Data Transmission Protocol

### HDLC Protocol & Zero Bit Insertion Technology
**HDCL Protocol**
It's called the *High-Level Data Link Control*. It's a bit-oriented data link control protocol which does not depend on any character set or code set. 
It supports two transmissions:
- **Asynchronous transmission:** Data is transmitted in bytes, and additional start and stop bits are used to mark the start and end of each byte.
- **Synchronous transmission:** Data signals are transmitted in a fixed clock cycle

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/a01371e9-14b2-4649-9907-b7c222821dc3)


Its structure goes like this:
- **Flag field F:** Because the bit sequence of other information may be the same as that of the flags fields during transmission, the HDLC protocol introduces ***zero-bit insertion, which ensures the uniqueness of the flags field and the transparency of data transmission***.
- **Address field A:** It specifies the address of the receiver. The address field is one byte by default and can be used to address a maximum of 254 hosts. It can also be extended to multiple bytes. An address field set to all 1s indicates that the address is a broadcast address. An address field set to all 0s is invalid. For Ethernet, the length of the address field in an HDLC frame is 6 bytes.
- **Control field C:** It is used to indicate the frame type and specify various commands and response modes to monitor the link. The default length is 1 byte, but it can be extended to 2 bytes. For Ethernet, the length of the control field in an HDLC frame is 2 bytes.
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/9ecc0111-43b9-42bf-a80a-ab805e779095)

	- The frames can be classified into three types: information frames, supervision frames, and unnumbered frames.
- **Information field I:** It carries data packets from the network layer, that is, IP data packets. Its length is determined by the frame check sequence, or FCS field or the cache capacity of the communication node. The upper limit is 1000 to 2000 bits, and the lower limit is 0. That is, the information field of the supervision frame, called the S frame, can be 0. For Ethernet, the length of the information field ranges from 46 bytes to 1500 bytes
- ** Frame check field FCS:** This field is used to detect errors between two flags fields. The default value is 2 bytes, but it can be extended to 4 bytes for Ethernet. The cyclic redundancy check or CRC technology is used to detect errors from the first bit of the address field to the last bit of the information field. CRC, also known as polynomial code, is the most widely used and effective error control code in data link communication between LANs and WANs

**How does Zero-Bit Insertion works**
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/e9b2e5de-f66c-4388-b9c9-4a6d470f6744)
### TCP/IP Protocol (1)
It refers to the *Transmission Control Protocol* and the *Internet Protocol*. It's a connection-oriented, reliable and byte stream based transport layer communication protocol which is applicable to multiple network applications. It is network independent because it limits the packet length (A packet must be less than 64kb, if it is bigger, it needs to be fragmented).

- It enables communication between two processes but does not support BUM

**IP**
It includes three aspects:
- IP addressing scheme
- Packet encapsulation format
- Packet forwarding rule

**Fields in a TCP/IP Packet**

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/e1d6061e-1375-44a3-8fa6-ec7f8a527024)


- **First row:** It's used to identify the application processes at both ends of the connection
- **Second row:** It's the number of each sent byte rather than the number of each TCP packet.
- **Third row:** It indicates the sequence number of the next byte to be received in the attached response mode. In this way, the peer end is informed that the bytes before the sequence number have been received correctly.
- **Fourth row:** Size of the TCP header - Describes the purpose and content of the TCP field (URG, ACK, PSH, RST, SYN and FIN). - Window is used to control the amount of data that can be sent by the peer end.
- **Fifth row:** It checks the TCP header data - It indicates the position of urgent data in the window. Data marked as urgent should be transmitted prior to other data.
- **Sixth row:** It indicates the maximum segment size, or MSS option, which can be used only during connection establishment - The padding is used to ensure that the length of options is an integer multiple of 32 bits.

**How does TCP/IP works**
It works by connection establishment and release:
- TCP Connection Setup.
- TCP Connection Release.

**TCP Connection process**
>💡 The arrows are indicating the handshakes in order, being three in total

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/9aeb5e68-064f-48a3-a7c7-774be281728c)


**TCP Control Traffic**
- TCP flow control is used to overcome mismatches between the processing capabilites of the sender and receiver.
- The simplest traffic control solution is that the receiver notifies the sender of its processing capabilites, and then the sender sends packets accordingly.
- The window size field in a TCP packet is used to exchange the size of the receive window between the sender and receiver. This is because sometimes the receiver may have a slow cache, etc.

> 💡 **Congestion:** It refers to transmission of too many packets in a communication subnet leading to the noticeable deterioration of network transmission performance

> 💡 In order to solve that, TCP/IP uses the fast retransmit and recovery algorithm for avoiding losing packets when the network is working at his fullest.

### TCP/IP Protocol (2)
**IP** (Network layer) provides connectionless packet transmission and is responsible only for transmitting packets to the destination node. It does not perform authentication or send acknowledgments to confirm whether the transmission is correct, nor does it ensure the correct sequence of packets. The reliability is implemented by TCP (Transport layer)

**Structure**
It consists of:
- **Packet header:** It stores the IP-specific control information
- **Data area:** It contains upper-layer (TCP) data to be transmitted over IP.

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/2c0eb8ad-8044-4bb1-a933-0c698ed38ba6)


 - **Version:** Whether the IP address is IPv4 or IPv6.
 - **Header length:** It specifies the number of 32-bit words forming the header.
 - **Service type:** IP packet priority.
 - **Total length:** It indicates the total length of an IP packet, incluiding the header and the data area.
 - **Identification:** It is used to identify an IP packet
 - **Flags:** The DF bit is used to indicate whether the IP packet can be fragmented, and the MF bit is used to indicate whether there is a subsequent fragment, and the last one is reserved.
 - **Offset:** It specifies the offset of a particular fragment relative to the beginning of the original IP packet. It's mandatory for fragment reassembly.
 - **Time to live:** It indicates the maximum transmission distance of an IP packet on the network. It decreases by one each time the IP packet passes through a router.
 - **Protocol:** The value is 6 for TCP and 17 for UDP.
 - **Checksum:** It's used to ensure the integrity of the IP packet header.
 - **Source IP address:** It indicates the IP address of the source host of the IP packet
 - **Destination IP address:** It indicates the IP address of the target host that receives the IP packet
 - **Options (variable length):** It's used for alignment
 - **Padding (variable length)**
 - **Payload**

**IP Routing Protocol**
On an IP network, routers select routes. By running certain routing protocols, a router searches for an optimal route to the destination host or network of an IP packet and forwards the packet.

A routing protocol is a network protocol that specifies the packet forwarding mode. The router forwards the received data according to the routing table. The forwarding policy may be manually specified, for example, by using methods such as static routing and policy-based routing.

Some of them are: RIP, IGRP, EIGRP, OSPF, IS-IS and BGP

>💡 A router uses a routing algorithm to find the optimal route to the destination. The routing algorithm is also called path selection algorithm. It aims to find the path with the lowest cost from the source router to the destination router. Some parameters are the hop count, the delay, and the communication time of the packet transmission.

## Network Link Contention Protocol
Most LANs adopt the bus structure. When a large number of network nodes share the same communication link or communication channel, ensuring fair allocation of the link or channel is the main problem that needs to be solved. Multi-access protocols, also called media access control (MAC) protocols, are commonly used to solve this problem. They can be divided into two types: *contention-based protocols* and *collision-free protocols*.

- **Contention-based protocol:** Before sending data, a node does not need to coordinate the right of using a channel with another node. Instead, it sends the data as soon as the data is available. In this case, if multiple nodes send data at the same time, a collision occurs. Typical contention-based protocols include the CSMA/CD protocol.
- **Collision-free protocol:** Each node completes the transmission process according to the specific arbitration policy, which avoids collisions in the data transmission process. A token protocol is a typical collision-free protocol. ***The basic idea is that a node must obtain a token (A special data frame) before sending data***. Examples of these are token buses and token rings.

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/675e8228-e710-4992-9d49-b872180ca47b)

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/6a9172ca-3ebe-4e72-bc48-3de213ced83c)


**CSMA/CD protocol**
It's a media access control (MAC) method for collision detection through carrier-sensing.

>💡 **Working process:**
> Before sending data, a network node first monitors whether a channel has a carrier. If the channel has no carrier, that is, the channel is idle, the data transmission starts. 
>![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/a3aeb0c1-382e-4639-8a91-133703da1d3d)
## Network Resource Sharing Protocol
**Summary of Network Resource Sharing Protocols:**
| **Protocol Name** |    **Protocol Description**   | **Application Scenarios**                |
|:-----------------:|:-----------------------------:|------------------------------------------|
|        HTTP       | Hypertext Transfer            | Resource search                          |
|        FTP        | File Transfer Protocol        | File upload and download                 |
|        HTML       | Hyper Text Markup Language    | Web page making                          |
|        SMTP       | Simple Mail Transfer Protocol | Email sending and inter-mailbox delivery |
|        POP        | Post Office Protocol          | Email receiving                          |
|       Telnet      | Remote login protocol         | Login to a remote host system            |

### Resource Search Engine and Web Service Agreement
**World Wide Web, WWW**
It is a global, dynamic, interactive, and cross-platform distributed graphics information system based on the HTTP. The Web uses a new browser/server (B/S) model, which is an improvement of the client/server (C/S) model.

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/9d47f651-8dfe-4123-a81b-0db56693e270)

**Resource request process for Web services**
1. A user enters a domain name in the address bar of the browser.
2. DNS is used to resolve the domain name to obtain the IP address of the domain name.
3. Based on the IP address, a Web application server is located and a TCP three-way handshake connection is initiated.
4. After a TCP connection is set up, and HTTP request packet is sent, such as the request packet.
5. The server responds to the HTTP request, and the browser obtains the response packet that contains the HTML code
6. The browser parses the returned HTML code, and then requests resources in the HTML code, such as JavaScript, CSS, and images. These resources are loaded for a second time
7. The browser renders the HTML code and the requested resources, and then presents the resources to the user.
8. The server releases the TCP connection

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/791778f8-63ac-464c-a656-032380f8efd9)

### Email Services
**Model of an email service**
In the email system, email senders and recipients are clients and use email proxies such as Hotmail and Foxmail to edit, send, and receive emails.

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/9921c79e-49e9-4944-8d98-18672a31d30f)

**Typical Email Service Protocols**
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/04a6737a-1063-456b-ba8e-41db069c8c4c)

### IoT Concepts, Models, and Protocols
**What is the Internet of things**
- In 1998, MIT proposed a unique numbering scheme based on the radio frequency identification (RFID) technology, that is, the electronic product code (EPC).
- In 1999, the MIT Auto-ID Lab first proposed the concept of IoT.
- At that time, IoT was simply defined as an approach to the combine item coding, RFID, and Internet technologies to implement automatic identification and information sharing of items through the Internet.

But the general definition goes like this: IoT serves as a network that enables information sensing devices such as radio frequency identification (RFID) devices, infrared devices, GPS devices and laser scanners to connect any item to the Internet for information exchange and communication based on agreed protocols

**RFID**
RFID is a non-contact fully automatic identification technology. Its basic principle is to implement non-contact transmission of object information using the transmission feature of an electromagnetic signal and space coupling. This allows a static or moving object or person to be automatically identified in a non-contact manner.

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/499edcac-8bc3-47dc-be39-0ae929f663af)

- **RFID tag:** Each RFID tag has a globally unique electronic code. You can attach it to an object to uniquely identify the object. It can be read and modified in real time.
- **RFID reader:** It is a device that uses the radio frequency (RF) technology to read and write electronic tag information

**RFID Reading Protocol**
>💡 The most popular in terms of secure, is the hash-based security authentication protocol which encrypts messages using the hash algorithm. 

An RFID reader uses a three-way handshake authentication protocol in the reading process. This is the **RFID Reading Process:**
1. The RFID reader sends information to the RFID tag. After receiving the information, the RFID tag can determine that its receiving function is normal.
2. The RFID tag sends information to the RFID reader as a response. After receiving the information, the RFID reader can determine that its transmitting and receiving functions are normal.
3. The RFID reader sends information to the RFID tag. After receiving the information, the RFID tag can determine that its transmitting function is normal

By doing that, it's possible to determine that the established connection is reliable

## Computer Network Equipment and Configuration Management
To connect to devices on a LAN, a MAN, or a WAN, transmission media such as Ethernet cables or network interfaces (such as an RJ45) is generally used. These devices include intra-network (NICs, repeaters, hubs, and switches) and inter-network interconnection devices (Bridges, routers, and gateways).

**Intra-network interconnection devices** 
They include NICs, repeaters, hubs, and switches.

- **NIC:** It's known as a network adapter, it connects a computer and a transmission medium to enable the computer to transmit data to another computer
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/59611d4d-8541-4df2-9547-b05dc6ff1f79)

- **Network Transmission medium:** Typical network transmission media are twisted pairs (Star networks), coaxial cables (Bus networks) and optical cables (Backbone network connection).
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/14948f36-75f6-41a7-b2a8-64d12b4d12cf)

- **Repeater and hub:** A repeater is the simplest device for interconnecting LANs. It works at the physical layer of the OSI model to connect different physical media and transmit data packets over them. ***A repeater is also called a Hub*** which has multiple ports. Each port of a hub is a repeater.
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/d6755a64-f330-4663-a52d-df3b52d796f6)

- **Switch:** A switch is a device that exchanges information in a communication system. It can provide an exclusive electrical signal path for any two network nodes connected to the switch and transmit data between multiple ports at the same time. ***Each port can be regarded as an independent network segment.*** The network devices connected to the port can use all the bandwidth without competing with other devices. 
There are three types of switches based on their positions on the network: *Access switches (Layer 1), Aggregation switches (Layer 2) and Core Switches (Layer 3)*.
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/1e592b41-c39b-4aba-a68f-30c19f806dc6)


**Types of network Switches**
- **Access switch:** Directly connect user terminals to the network. They are inexpensive and have a high port density. In therms of transmission speed, most access switches provide multiple ports of 10 Mbit/s, 100 Mbit/s, or 1000 Mbit/s with auto-negotiation.
- **Aggregation switch:** It aggregates traffic of multiple access switches between buildings. It must be able to process all traffic from access layer devices and provide uplinks to the core layer. Therefore, aggregation switches offer higher performance, fewer interfaces, and higher switching rates than access switches.
- **Core switch:** It connects multiple aggregation switches to provide an optimized and reliable backbone transmission structure though high-speed forwarding communication. They have to have higher reliability, performance, and throughput.
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/af0defdd-ead9-49d9-b1e3-96d1c7c789ae)
## Inter-network Interconnection Devices
They include: Bridges, routers and gateways.
**Bridge** 
It's a device that implements network interconnection at the data link layer. It works at the MAC sub-layer of the Ethernet and functions as a storage and forwarding device based on data frames. It's used to combine two or more LANs that use the same communication protocol transmission media and addressing structure.

It provides the addressing and path selection functions. It can detect the source and destination address of a data frame that enters the bridge.
It can screen or filter:
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/5a50d554-45fb-477e-94bb-36614801c048)

It can isolate the information that does not need to be transmitted between networks, greatly reducing the network load and improving the network performance. It also has the ***Network Management function*** that can monitors the status of the extended network to better adjust the network topology. It cannot identify or filter broadcast information.

**Router**
The main difference between routing and switching is that switching occurs at the data link (Layer 2) whereas routing occurs on the Network layer (Layer 3).

A router functions as a hub of the Internet. It's used to connect LAN and WAN devices on the internet. It automatically selects and sets routes based on channel conditions and sends signals along the optimal path in sequence
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/a9387a10-517e-4de9-a208-cceb5e64b084)

- **Wireless router:** It's a communication device used to connect wired and wireless networks using the wi-fi technology. It can be configured with a service set identifier **(SSID)**. The SSID is a case-sensitive character string of up to 32 bytes, it can be a physical location, a person name, a company name, etc.
For protecting this routers, WPA, WPA2 and WPA3 are proposed.

**Gateway**
It's a computer system or device that functions as a conversion unit. It's a translator between two systems that use different communication protocols, data formats or languages, or even completely different architectures. It repackages the received information to meet the requirements of the destination system, and it can provide filtering and security functions.
In a resume, they can:
- Protocol conversion between networks.
- Packet storage, forwarding, and flow control.
- Application layer interworking and inter-network management.
- Providing virtual circuit interfaces and corresponding services

## Network Device Management and Configuration Methods

**What is a network management**
A network management is a network service that monitors, controls, and records:
- The performance of network resources.
- Usage of network resources.
- Make the network work effectively.
- Ensure services are of a certain quality.

It involves:
- The use, integration, and coordination of hardware.
- Use of software and human resources to monitor, test, configure, analyze, asses and control network resources.

Doing that, requirements of the network such as real-time running performance and service quality can be met at a reasonable cost.

**Simple Network Management Protocol (SNMP)**
It has become a *de facto* industry standard in the network management field and enjoys wide support and application. Most network managements systems and platforms use SNMP for management

**Virtual Local Area Network (VLAN)**
It's a logical segment for connecting network users to the ports of Layer 3 and Layer 2 switches, and ensures users are not restricted by their physical locations.
They can be configured based on the user locations, functions, departments, or applications and protocols used by network users.
It can be configured on a single switch or across switches. They are divided by two:
- **Static VLAN:** It refers to a VLAN whose ID is statically bound to switch ports.
- **Dynamic VLAN:** It refers to a VLAN that a switch automatically allocates to a host after it connects a port on the switch.

**Dynamic VLAN**
Dynamic VLANs can be configured on the following modes:
- **MAC address-based VLAN:** The MAC addresses of all hosts are added to the VLAN management database.
- **IP-based VLAN:** It used the mapping between the subnet ID and VLAN ID. Even if the NIC of the host changes, as long as the NIC's IP address remains unchanged, the switch can automatically set the VLAN ID corresponding to the subnet IP of the host.
- **User-based VLAN:** The users determine the VLAN to which they belong through configurations on the software.

**Versatile Routing Platform (VRP)**
It's an operating system platform for data communication products, developed by **Huawei** to support all IP/ATM-based architectures.
It implements multiple protocols.
This is the VRP Architecture:
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/745f6a5b-3fce-4894-a2ad-9b1f5c940e5b)

**How to configure and manage VLANs and VRP**
**VLAN Lab Summary**
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/20861fcf-c22a-4471-8c2d-789a50d6aeb7)

**Huawei VRP System Lab Summary**
![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/49aa6cfe-da05-4514-b12e-6d6c18cc7069)



