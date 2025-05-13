
# Chapter 2: Network Models – Detailed Notes

---

## 2-1 Layered Tasks

### Introduction
In real life, we use layers to break down complex tasks into simpler ones. The same idea is used in computer networks to handle data communication efficiently.

### Example: Sending a Letter
Imagine you are sending a physical letter to a friend:
- **You (Sender)** write the message.
- **Postal Service (Carrier)** delivers the letter.
- **Your Friend (Receiver)** reads it.

Each part of the process has a specific task. The postal system makes it easy for people to communicate without handling the entire delivery process themselves. This is similar to how data travels in a network — each layer has a job.

### Hierarchy of Communication
- The **top layer** makes the decision to communicate.
- The **middle layers** help with processing and formatting the message.
- The **bottom layer** physically sends the data.

---

## 2-2 The OSI Model

### What is OSI?
The **Open Systems Interconnection (OSI)** model was developed by the **International Standards Organization (ISO)** in the late 1970s. It's a reference model that defines how data should be transmitted across a network in seven layers.

### Layered Architecture
Each layer in the OSI model:
- Communicates with its **peer layer** on another system.
- **Receives services** from the layer below.
- **Provides services** to the layer above.

### Peer-to-Peer Communication
When you send a message:
- Each layer adds its own information (headers).
- On the receiving end, the layers remove this information in reverse order.

This process is called **encapsulation** when sending and **decapsulation** when receiving.

---

## 2-3 Layers in the OSI Model

### 1. Physical Layer
- Deals with **transmitting raw bits** over a communication channel.
- Involves cables, switches, voltages, and physical connections.

**Note:** It moves data from one node to another without interpreting it.

### 2. Data Link Layer
- Responsible for **node-to-node delivery** using frames.
- Adds **MAC (Media Access Control)** addresses to identify devices.
- Performs **error detection and correction**.

**Note:** Ensures that data sent from one device is properly received by the next device.

### 3. Network Layer
- Manages **source-to-destination delivery** across multiple networks.
- Uses **IP (Internet Protocol)** addresses to identify devices globally.
- Handles **routing** of packets.

**Note:** Makes decisions on how to reach the destination.

### 4. Transport Layer
- Ensures reliable delivery from **process to process**.
- Common protocols: **TCP** (reliable), **UDP** (faster, but unreliable).
- Breaks messages into smaller segments.

**Note:** Keeps track of message delivery and ensures no duplication or loss.

### 5. Session Layer
- Controls sessions between applications.
- Manages **dialog control**, i.e., who transmits and when.
- Helps in **synchronization** during long transmissions.

**Note:** Like a phone call connection — opening, talking, closing.

### 6. Presentation Layer
- Deals with **data translation**, **encryption**, and **compression**.
- Makes sure data from sender is readable to receiver.

**Note:** Converts formats like JPG, MP3, etc.

### 7. Application Layer
- Closest to the **end user**.
- Provides services like email, web browsing, file transfers.
- Protocols: **HTTP, FTP, SMTP, DNS**

**Note:** Interface for user-network interaction.

---

## 2-4 TCP/IP Protocol Suite

### Introduction
The **TCP/IP model** is a practical and widely used model that predates the OSI model. Originally, it had **4 layers**, but for easier comparison with OSI, it is now often described in **5 layers**.

### Original 4 Layers
1. **Host-to-Network Layer**
   - Deals with physical transmission.
   - Corresponds to both **Physical** and **Data Link** layers in OSI.

2. **Internet Layer**
   - Equivalent to OSI’s **Network Layer**.
   - Responsible for **routing** and **IP addressing**.

3. **Transport Layer**
   - Same as OSI’s **Transport Layer**.
   - Responsible for reliable transmission.

4. **Application Layer**
   - Combines OSI's **Application**, **Presentation**, and **Session** layers.

### Revised 5 Layers (for OSI Comparison)
1. **Application Layer** – user interaction
2. **Transport Layer** – process communication
3. **Network Layer** – routing
4. **Data Link Layer** – node-to-node delivery
5. **Physical Layer** – bit transmission

### Diagram Comparison

```
TCP/IP Model           OSI Model
---------------        --------------------------
Application            Application
                       Presentation
                       Session

Transport              Transport

Internet               Network

Host-to-Network        Data Link
                       Physical
```

---

## 2-5 Addressing

### Why Addressing?
Every device and service on a network needs a unique identifier. TCP/IP uses **four types of addresses** to deliver data accurately.

### 1. Physical Address
- Also called **MAC address**.
- Assigned to network interface hardware.
- Used for **local delivery**.
- **Example:** 07:01:02:01:2C:4B (48-bit, written in hexadecimal)

### 2. Logical Address
- Used for **global identification**.
- Assigned by the network (IP address).
- Helps in routing data across different networks.

### 3. Port Address
- Identifies a **specific process or service**.
- Each service runs on a specific port.
- **Example:** Port 80 for HTTP, Port 25 for SMTP.

### 4. Specific Address
- Combination of IP and Port address.
- Identifies an **exact process** on a specific device.

### Example 2.1
Two devices with MAC addresses `10` and `87` exchange frames over a LAN. The sender uses `10`, and the receiver uses `87`.

### Example 2.2
A typical MAC address:  
**07:01:02:01:2C:4B** – a 6-byte (48-bit) physical address.

### Example 2.3
A router connected to 3 networks has 3 pairs of physical and logical addresses (one per interface). A computer connected to one network has only one pair.

### Example 2.4
Computer A runs processes with port addresses `a`, `b`, and `c`. Computer B runs processes `j` and `k`. If `a` wants to talk to `j`, it uses port addressing. Physical address may change during transit, but port and IP address remain constant.

### Example 2.5
A port address is a **16-bit number**, such as `753`.

### Final Note
- **MAC (physical) addresses** change from hop to hop.
- **IP and port addresses** stay constant throughout the journey.

---

