# Data Communications and Networking - Chapter 1 Solutions
## Behrouz A. Forouzan

---

## 1.7.2 Questions

### Q1-1. Identify the five components of a data communications system.

The five components of a data communications system are:
1. **Message** - The information (data) to be communicated
2. **Sender** - The device that sends the data message
3. **Receiver** - The device that receives the message
4. **Transmission Medium** - The physical path by which a message travels from sender to receiver
5. **Protocol** - A set of rules that govern data communications

### Q1-2. What are the three criteria necessary for an effective and efficient network?

The three criteria are:
1. **Performance** - Can be measured in terms of transit time and response time
2. **Reliability** - Measured by frequency of failure, recovery time, and catastrophic failure
3. **Security** - Protecting data from unauthorized access, viruses, and damage

### Q1-3. What are the advantages of a multipoint connection over a point-to-point one?

Advantages of multipoint connection:
- **Cost-effective** - One single link can serve multiple devices
- **Reduced cabling** - Less physical infrastructure required
- **Easier maintenance** - Fewer connections to manage
- **Scalability** - Easy to add new devices to the network

### Q1-4. What are the two types of line configuration?

The two types of line configuration are:
1. **Point-to-Point** - Provides a dedicated link between two devices
2. **Multipoint** - More than two specific devices share a single link

### Q1-5. Categorize the four basic topologies in terms of line configuration.

- **Mesh Topology** - Point-to-point connections between every pair of devices
- **Star Topology** - Point-to-point connections between each device and a central hub
- **Bus Topology** - Multipoint connection where all devices share a single communication line
- **Ring Topology** - Point-to-point connections in a circular arrangement

### Q1-6. What is the difference between half-duplex and full-duplex transmission modes?

- **Half-duplex** - Communication can flow in both directions, but only one direction at a time (like walkie-talkies)
- **Full-duplex** - Communication can flow in both directions simultaneously (like telephone conversations)

### Q1-7. Name the four basic network topologies, and cite an advantage of each type.

1. **Mesh Topology** - Provides redundancy and fault tolerance
2. **Star Topology** - Easy to install and reconfigure; centralized management
3. **Bus Topology** - Easy to install and requires less cable length
4. **Ring Topology** - Equal access for all stations; no collisions

### Q1-8. For n devices in a network, what is the number of cable links required for a mesh, ring, bus, and star topology?

- **Mesh Topology** - n(n-1)/2 links
- **Ring Topology** - n links
- **Bus Topology** - 1 backbone link (plus drop lines)
- **Star Topology** - n links

### Q1-9. What are some of the factors that determine whether a communication system is a LAN or WAN?

Factors include:
- **Geographic coverage** - LANs cover small areas (building, campus), WANs cover large areas (cities, countries)
- **Ownership** - LANs are typically privately owned, WANs often use public infrastructure
- **Data rates** - LANs typically have higher data rates
- **Error rates** - LANs have lower error rates than WANs

### Q1-10. What is an internet? What is the Internet?

- **internet** (lowercase) - A general term for interconnected networks
- **Internet** (uppercase) - The specific worldwide network of interconnected networks using TCP/IP protocols

### Q1-11. Why are protocols needed?

Protocols are needed to:
- Define the format and order of messages
- Define actions taken on message transmission and receipt
- Ensure reliable communication between different systems
- Provide standardization for interoperability

### Q1-12. In a LAN with a link-layer switch, does the switch need to have an address?

No, a link-layer switch does not need to have an address for basic switching operations. It operates at the data link layer and forwards frames based on MAC addresses in its switching table. The switch is transparent to the hosts.

### Q1-13. How many point-to-point WANs are needed to connect n LANs if each LAN should be able to directly communicate with any other LAN?

The number of point-to-point WANs needed is: **n(n-1)/2**

This creates a full mesh topology between the LANs.

### Q1-14. When we use local telephones to talk to a friend, are we using a circuit-switched network or a packet-switched network?

We are using a **circuit-switched network**. The telephone system establishes a dedicated circuit for the duration of the call.

### Q1-15. When a resident uses a dial-up or DSL service to connect to the Internet, what is the role of the telephone company?

The telephone company provides:
- The physical transmission medium (telephone lines)
- Infrastructure for connecting to the Internet Service Provider (ISP)
- Last-mile connectivity to homes and businesses

### Q1-16. What is the first principle we discussed in this chapter for protocol layering that needs to be followed to make the communication bidirectional?

The first principle is that **each layer needs to be able to perform two opposite tasks**, one in each direction.

### Q1-17. Explain the difference between an Internet draft and a proposed standard.

- **Internet Draft** - A working document with no official status; preliminary version of an RFC
- **Proposed Standard** - A specification that has been approved and is stable enough for implementation

### Q1-18. Explain the difference between a required RFC and a recommended RFC.

- **Required RFC** - Must be implemented by all systems claiming conformance to the Internet protocol suite
- **Recommended RFC** - Should be implemented but is not mandatory for basic conformance

### Q1-19. Explain the difference between the duties of the IETF and IRTF.

- **IETF (Internet Engineering Task Force)** - Focuses on short-term engineering and standardization issues
- **IRTF (Internet Research Task Force)** - Focuses on long-term research and development

---

## 1.7.3 Problems

### P1-1. What is the maximum number of characters or symbols that can be represented by Unicode?

Unicode uses different encoding schemes:
- **UTF-8, UTF-16, UTF-32** can represent up to **1,114,112** code points (2^20 + 2^16)
- However, not all code points are assigned to characters

### P1-2. A color image uses 16 bits to represent a pixel. What is the maximum number of different colors that can be represented?

Maximum colors = 2^16 = **65,536 colors**

### P1-3. Assume six devices are arranged in a mesh topology. How many cables are needed? How many ports are needed for each device?

- **Cables needed**: n(n-1)/2 = 6(5)/2 = **15 cables**
- **Ports per device**: n-1 = 6-1 = **5 ports per device**

### P1-4. For each of the following four networks, discuss the consequences if a connection fails.

a. **Five devices in mesh topology**: Other devices remain connected through alternative paths; high fault tolerance

b. **Five devices in star topology**: If hub fails, entire network fails; if one device connection fails, only that device is affected

c. **Five devices in bus topology**: If backbone fails, entire network fails; if a device connection fails, only that device is affected

d. **Five devices in ring topology**: If one connection fails, the entire ring is broken unless there's a backup path

### P1-5. We have two computers connected by an Ethernet hub at home. Is this a LAN or a WAN?

This is a **LAN** because:
- Limited geographical area (home)
- High data rate
- Private ownership
- Low error rate

### P1-6. In the ring topology, what happens if one of the stations is unplugged?

The ring is broken and communication fails for all stations, unless the ring has redundancy or bypass mechanisms.

### P1-7. In the bus topology, what happens if one of the stations is unplugged?

The unplugged station loses connectivity, but other stations can continue communicating normally since they remain connected to the bus.

### P1-8. Performance is inversely related to delay. When we use the Internet, which of the following applications are more sensitive to delay?

a. **Sending an e-mail** - Not sensitive to delay
b. **Copying a file** - Moderately sensitive to delay
c. **Surfing the Internet** - Most sensitive to delay (real-time interaction)

### P1-9. When a party makes a local telephone call to another party, is this a point-to-point or multipoint connection?

This is a **point-to-point connection** because it establishes a dedicated path between two specific parties for the duration of the call.

### P1-10. Compare the telephone network and the Internet. What are the similarities? What are the differences?

**Similarities:**
- Both provide communication services
- Both use network infrastructure
- Both connect users across distances
- Both use switching techniques

**Differences:**
- **Telephone Network**: Circuit-switched, connection-oriented, primarily voice
- **Internet**: Packet-switched, connectionless, multimedia data
- **Telephone Network**: Dedicated bandwidth during call
- **Internet**: Shared bandwidth, variable delay
- **Telephone Network**: Centralized control
- **Internet**: Distributed control
