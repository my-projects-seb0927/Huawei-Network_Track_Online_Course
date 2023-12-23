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

![imagen](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/1a116617-1f1a-4256-81a6-5ff57a572063)

****




