
# Chapter 2: Network Models

---

## 2-1 Layered Tasks

### Overview
In communication systems, tasks are often divided into layers. This makes complex processes easier to manage and understand.

### Example: Sending a Letter
- **Sender:** Writes and sends the letter.
- **Carrier (Post Office):** Delivers the letter.
- **Receiver:** Receives and reads the letter.

This process can be compared to data communication systems, where different tasks are handled by different layers.

---

## 2-2 The OSI Model

### Overview
The **Open Systems Interconnection (OSI)** model, developed by **ISO**, standardizes network communications using a layered approach.

### Key Concepts:
- **Layered Architecture:** Each layer provides services to the one above it and receives services from the one below.
- **Peer-to-Peer Processes:** Same-layer processes on different machines communicate logically.
- **Encapsulation:** Each layer adds headers to data as it moves down the stack.

### OSI Layers:
1. **Physical**
2. **Data Link**
3. **Network**
4. **Transport**
5. **Session**
6. **Presentation**
7. **Application**

---

## 2-3 Layers in the OSI Model

### Layer Functions:

1. **Physical Layer**
   - Transmits raw bits over a physical medium.
   - Example: Ethernet cable signals.

2. **Data Link Layer**
   - Transfers frames from one node to another.
   - Ensures error detection and correction.

3. **Network Layer**
   - Manages packet delivery across multiple networks.
   - Example: IP addressing and routing.

4. **Transport Layer**
   - Ensures complete data transfer between processes.
   - Example: TCP ensures reliable delivery.

5. **Session Layer**
   - Manages sessions and dialog control between systems.

6. **Presentation Layer**
   - Translates, compresses, and encrypts data.

7. **Application Layer**
   - Provides network services directly to applications.
   - Examples: Email (SMTP), Web (HTTP)

---

## 2-4 TCP/IP Protocol Suite

### Overview
The TCP/IP model has fewer layers than the OSI model but provides a practical framework for real-world network protocols.

### Original TCP/IP Model (4 Layers):
1. **Host-to-Network**
2. **Internet**
3. **Transport**
4. **Application**

### Expanded TCP/IP Model (5 Layers):
1. **Physical**
2. **Data Link**
3. **Network (Internet)**
4. **Transport**
5. **Application**

| TCP/IP Layer     | OSI Equivalent                     |
|------------------|------------------------------------|
| Application      | Application, Presentation, Session |
| Transport        | Transport                          |
| Network          | Network                            |
| Data Link        | Data Link                          |
| Physical         | Physical                           |

---

## 2-5 Addressing

### Overview
Communication in a TCP/IP network involves multiple levels of addressing.

### Types of Addresses:

1. **Physical Address**
   - Unique hardware identifier (e.g., MAC address).
   - Example: `07:01:02:01:2C:4B`

2. **Logical Address**
   - IP address used for routing.
   - Assigned by the network and can change.

3. **Port Address**
   - Identifies specific processes/services.
   - Example: Port 80 for HTTP.

4. **Specific Address**
   - Combination of logical and port address to identify a specific application on a device.

### Key Points:
- **Physical addresses** change from hop to hop.
- **Logical and port addresses** remain the same from source to destination.

### Example:
- A computer sends data from process `a` to process `j` using IP and port addresses, while MAC addresses change along the path.

---

