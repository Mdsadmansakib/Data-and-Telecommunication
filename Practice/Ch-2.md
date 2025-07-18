# Data Communications and Networking - Chapter 2 Solutions
## Network Models - Behrouz A. Forouzan

---

## 2.5.2 Questions

### Q2-1. What is the first principle we discussed in this chapter for protocol layering that needs to be followed to make the communication bidirectional?

The first principle is that **each layer needs to be able to perform two opposite tasks**, one in each direction. For example, a layer should be able to both encrypt and decrypt data, or both compress and decompress data.

### Q2-2. Which layers of the TCP/IP protocol suite are involved in a link-layer switch?

A link-layer switch is involved with:
- **Physical layer** - For electrical/optical signal transmission
- **Data-link layer** - For frame switching and MAC address processing

### Q2-3. A router connects three links (networks). How many of each of the following layers can the router be involved with?

a. **Physical layer**: **3 layers** (one for each link/network interface)
b. **Data-link layer**: **3 layers** (one for each link/network interface)

### Q2-4. In the TCP/IP protocol suite, what are the identical objects at the sender and receiver sites when we think about the logical connection at the application layer?

The identical objects are **messages** or **application data units**. The application layer creates the same type of data unit at both sender and receiver sites.

### Q2-5. A host communicates with another host using the TCP/IP protocol suite. What is the unit of data sent or received at each of the following layers?

a. **Application layer**: **Message**
b. **Network layer**: **Datagram** (or packet)

### Q2-6. Which of the following data units is encapsulated in a frame?

Both options can be encapsulated in a frame:
- **a. A user datagram** - Yes, UDP datagrams are encapsulated in frames
- **b. A datagram** - Yes, IP datagrams are encapsulated in frames

### Q2-7. Which of the following data units is decapsulated from a user datagram?

**b. A segment** - A user datagram contains a segment (from the transport layer) plus UDP header.

### Q2-8. Which of the following data units has an application-layer message plus the header from layer 4?

**b. A user datagram** - Contains the application message plus the UDP header (layer 4).

### Q2-9. List some application-layer protocols mentioned in this chapter.

Common application-layer protocols include:
- **HTTP** (HyperText Transfer Protocol)
- **FTP** (File Transfer Protocol)
- **SMTP** (Simple Mail Transfer Protocol)
- **DNS** (Domain Name System)
- **Telnet**
- **POP3** (Post Office Protocol)
- **IMAP** (Internet Message Access Protocol)

### Q2-10. If a port number is 16 bits (2 bytes), what is the minimum header size at the transport layer of the TCP/IP protocol suite?

The minimum header size would be **4 bytes** (source port + destination port = 2 bytes + 2 bytes). However, practical transport protocols like UDP have additional fields, making UDP header 8 bytes minimum.

### Q2-11. What are the types of addresses (identifiers) used in each of the following layers?

a. **Application layer**: **Names** (domain names, URLs, email addresses)
b. **Network layer**: **Logical addresses** (IP addresses)
c. **Data-link layer**: **Physical addresses** (MAC addresses)

### Q2-12. When we say that the transport layer multiplexes and demultiplexes application-layer messages, do we mean that a transport-layer protocol can combine several messages from the application layer in one packet?

No, multiplexing/demultiplexing here refers to **directing data to/from the correct application processes** using port numbers. It means multiple applications can use the network simultaneously, and the transport layer ensures each message reaches the correct application based on port numbers.

### Q2-13. Can you explain why we did not mention multiplexing/demultiplexing services for the application layer?

The application layer is the **topmost layer** that directly serves user applications. There are no upper layers above it that need to be multiplexed or demultiplexed. The application layer creates the original messages that are then handled by lower layers.

### Q2-14. Assume we want to connect two isolated hosts together to let each host communicate with the other. Do we need a link-layer switch between the two?

**No**, we do not need a link-layer switch. Two hosts can be directly connected with a **point-to-point link** using appropriate cables (like crossover Ethernet cable) or wireless connection.

### Q2-15. If there is a single path between the source host and the destination host, do we need a router between the two hosts?

**No**, if there's only a single path and both hosts are on the same network, a router is not needed. Routers are required when **multiple paths exist** or when hosts are on **different networks** that need routing decisions.

---

## 2.5.3 Problems

### P2-1. Answer the following questions about Figure 2.2 when the communication is from Maria to Ann:

a. **Service provided by layer 1 to layer 2 at Maria's site**: Layer 1 (Physical) provides **bit transmission service** - converting layer 2 frames into electrical, optical, or radio signals for transmission over the physical medium.

b. **Service provided by layer 1 to layer 2 at Ann's site**: Layer 1 (Physical) provides **bit reception service** - converting received electrical, optical, or radio signals back into digital bits for layer 2 processing.

### P2-2. Answer the following questions about Figure 2.2 when the communication is from Maria to Ann:

a. **Service provided by layer 2 to layer 3 at Maria's site**: Layer 2 (Data-link) provides **frame transmission service** - reliable delivery of layer 3 packets to the next hop, including error detection and correction.

b. **Service provided by layer 2 to layer 3 at Ann's site**: Layer 2 (Data-link) provides **frame reception service** - reliable delivery of received frames to layer 3, including error detection and frame validation.

### P2-3. Assume that the number of hosts connected to the Internet at year 2010 is five hundred million. If the number of hosts increases only 20 percent per year, what is the number of hosts in year 2020?

Initial hosts (2010): 500 million
Growth rate: 20% per year
Time period: 10 years (2010 to 2020)

Using compound growth formula: Final = Initial × (1 + rate)^years
Final = 500 × (1.20)^10 = 500 × 6.1917 = **3,095.85 million hosts** (approximately **3.1 billion hosts**)

### P2-4. Assume a system uses five protocol layers. If the application program creates a message of 100 bytes and each layer adds a header of 10 bytes, what is the efficiency of the system?

Original message: 100 bytes
Headers added: 5 layers × 10 bytes = 50 bytes
Total transmitted: 100 + 50 = 150 bytes

Efficiency = (Application data / Total transmitted) × 100%
Efficiency = (100 / 150) × 100% = **66.67%**

### P2-5. Using the TCP/IP protocol suite to transfer a huge file, what are the advantages and disadvantages of sending large packets?

**Advantages of large packets:**
- **Lower overhead ratio** - Less header overhead per byte of data
- **Fewer packets to process** - Reduced processing load on routers
- **Better throughput** - More efficient use of bandwidth

**Disadvantages of large packets:**
- **Higher probability of errors** - Larger packets more likely to be corrupted
- **Increased retransmission cost** - More data lost if packet needs retransmission
- **Longer delays** - Takes more time to transmit each packet
- **Fragmentation issues** - May need to be fragmented if exceeding MTU

### P2-6. Match the following to one or more layers of the TCP/IP protocol suite:

a. **Route determination**: **Network layer** (IP routing)
b. **Connection to transmission media**: **Physical layer** (hardware interface)
c. **Providing services for the end user**: **Application layer** (user services)

### P2-7. Match the following to one or more layers of the TCP/IP protocol suite:

a. **Creating user datagrams**: **Transport layer** (UDP)
b. **Responsibility for handling frames between adjacent nodes**: **Data-link layer**
c. **Transforming bits to electromagnetic signals**: **Physical layer**

### P2-8. In Figure 2.10, when the IP protocol decapsulates the transport-layer packet, how does it know to which upper-layer protocol (UDP or TCP) the packet should be delivered?

The IP header contains a **Protocol field** that identifies the next layer protocol. Common values:
- **6** = TCP
- **17** = UDP
- **1** = ICMP

### P2-9. Assume a private internet uses three different protocols at the data-link layer (L1, L2, and L3). Can we say that we have demultiplexing at the source node and multiplexing at the destination node?

**No**, this is backwards. At the source node, we have **multiplexing** (combining data from upper layers for different data-link protocols). At the destination node, we have **demultiplexing** (separating received data to send to appropriate upper layers).

**Corrected Figure 2.10 would show:**
- Multiple data-link protocols (L1, L2, L3) at each node
- Network layer interfacing with all three protocols
- Each protocol handling frames for its specific link type

### P2-10. If we need to add encryption/decryption information at the application layer, does this mean adding a new layer to TCP/IP?

**Yes**, this would effectively add a **Security/Presentation layer** between the Application and Transport layers.

**Modified TCP/IP Stack:**
```
Application Layer
↓
Security/Presentation Layer (Encryption/Decryption)
↓
Transport Layer (TCP/UDP)
↓
Network Layer (IP)
↓
Data-Link Layer
↓
Physical Layer
```

### P2-11. Protocol layering for air travel round-trip:

**Air Travel Protocol Layers:**

**Outbound Journey:**
1. **Planning Layer**: Book flight, choose destination
2. **Check-in Layer**: Baggage checking, seat assignment
3. **Security Layer**: Security screening, boarding pass validation
4. **Boarding Layer**: Gate procedures, boarding aircraft
5. **Flight Layer**: Takeoff, flight navigation, landing
6. **Arrival Layer**: Unboarding, baggage claim

**Return Journey (Reverse Process):**
1. **Arrival Layer**: Baggage claim, unboarding
2. **Flight Layer**: Landing, flight navigation, takeoff
3. **Boarding Layer**: Boarding aircraft, gate procedures
4. **Security Layer**: Boarding pass validation, security screening
5. **Check-in Layer**: Seat assignment, baggage checking
6. **Planning Layer**: Choose destination, book flight

### P2-12. If a presentation layer is added to TCP/IP, where should it be positioned?

The **Presentation layer** should be positioned **between the Application and Transport layers**.

**Modified TCP/IP Protocol Suite:**
```
Application Layer (User services)
↓
Presentation Layer (Data formatting, encryption, compression)
↓
Transport Layer (TCP/UDP)
↓
Network Layer (IP)
↓
Data-Link Layer
↓
Physical Layer
```

### P2-13. In an internet, we change the LAN technology to a new one. Which layers in the TCP/IP protocol suite need to be changed?

Only the **bottom two layers** need to be changed:
- **Physical layer** - New hardware interfaces and signaling
- **Data-link layer** - New frame format and MAC protocols

**Upper layers remain unchanged** due to the layered architecture's independence principle.

### P2-14. Can an application-layer protocol written for UDP use TCP services without change?

**No**, the application cannot use TCP without changes because:
- **TCP is connection-oriented** (requires connection setup/teardown)
- **UDP is connectionless** (no connection management)
- **Different service models** (reliable vs. unreliable delivery)
- **Different programming interfaces** (socket API differences)

The application would need modification to handle TCP's connection-oriented nature.

### P2-15. Using the internet in Figure 1.11, show the layers and data flow when hosts on west and east coasts exchange messages.

**Protocol Stack at Each Point:**

**West Coast Host:**
```
Application → Message
Transport → Segment/Datagram
Network → Packet
Data-Link → Frame
Physical → Bits
```

**Intermediate Routers:**
```
Network → Packet (routing decisions)
Data-Link → Frame (local delivery)
Physical → Bits (signal transmission)
```

**East Coast Host:**
```
Physical → Bits
Data-Link → Frame
Network → Packet
Transport → Segment/Datagram
Application → Message
```

**Data Flow:**
1. West coast host encapsulates data down through all layers
2. Data transmitted through multiple networks and routers
3. Each router processes up to network layer for routing decisions
4. East coast host decapsulates data up through all layers
5. Reverse process for return communication
