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
3. The packet is transmitted to the network layer and encapsulated with an IP header **(Data Packet(**.
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
- **Synchronous transmission:** Data is transmitted in bytes, and additional start and stop bits are used to mark the start and end of each byte. Data signals are transmitted in a fixed clock cycle
- **Asynchronous transmission:** *You are not going to use it*

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
