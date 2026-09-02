#  NETWORK MODELS — OSI & TCP/IP

---

## 2.1 LAYERED TASKS

### The Concept of Layers

We use the concept of **layers** in everyday life. Consider sending a letter through the postal system — without the post office's services, the process would be incredibly complex.

The key players in any layered communication:

- **Sender** – initiates the communication
    
- **Receiver** – receives the communication
    
- **Carrier** – transports the communication
    

> **FIGURE 2.1 HERE** – _Tasks involved in sending a letter_

![Image](images/Pasted%20image%2020260901172359.png)

---

## 2.2 THE OSI MODEL

### Overview

- **ISO** (International Standards Organization) – established in 1947
    
- **OSI** (Open Systems Interconnection) – a standard model for network communications, introduced in the late 1970s
    

> **Remember:** ISO is the **organization**. OSI is the **model**.

---

### Key Concepts in the OSI Model

|Concept|Description|
|---|---|
|**Layered Architecture**|Divides network functions into 7 distinct layers|
|**Peer-to-Peer Processes**|Each layer communicates with its corresponding layer on another device|
|**Encapsulation**|Each layer adds its own header (control information) to the data as it moves down the stack|

> **FIGURE 2.2 HERE** – _Seven layers of the OSI model_

![Image](images/Pasted%20image%2020260901172520.png)

> **FIGURE 2.3 HERE** – _The interaction between layers in the OSI model_

![Image](images/Pasted%20image%2020260901172542.png)

> **FIGURE 2.4 HERE** – _An exchange using the OSI model_ 

![Image](images/Pasted%20image%2020260901172612.png)

---

## 2.3 LAYERS IN THE OSI MODEL — DETAILED BREAKDOWN

---

### Layer 1: Physical Layer

**Responsibility:** Movement of **individual bits** from one hop (node) to the next.

> **FIGURE 2.5 HERE** – _Physical layer_

![Image](images/Pasted%20image%2020260901185426.png)

**Key Functions:**

|Function|Description|
|---|---|
|**Physical Characteristics**|Defines the interface between device and transmission medium|
|**Representation of Bits**|Defines encoding (how 0s and 1s are converted to signals)|
|**Data Rate**|Number of bits sent per second|
|**Synchronization**|Sender and receiver clocks must be synchronized|
|**Line Configuration**|Point-to-point or multipoint|
|**Physical Topology**|How devices are physically connected|
|**Transmission Mode**|Simplex, half-duplex, or full-duplex|

---

### Layer 2: Data Link Layer

**Responsibility:** Moving **frames** from one hop (node) to the next.

> **FIGURE 2.6 HERE** – _Data link layer 

![Image](images/Pasted%20image%2020260901185742.png)
  
> FIGURE 2.7 HERE** – _Hop-to-hop delivery_

![Image](images/Pasted%20image%2020260901185939.png)

**Key Functions:**

|Function|Description|
|---|---|
|**Framing**|Divides bit stream into manageable data units (frames)|
|**Physical Addressing**|Defines sender/receiver using physical (MAC) addresses|
|**Flow Control**|Controls transmission speed across a single link|
|**Error Control**|Detects/retransmits damaged or lost frames; detects duplicates|
|**Access Control**|Determines which device controls the link at any given time|

---

### Layer 3: Network Layer

**Responsibility:** Delivery of **individual packets** from the **source host** to the **destination host**.

> **FIGURE 2.8 HERE** – _Network layer_

![Image](images/Pasted%20image%2020260901190032.png)

> **FIGURE 2.9 HERE** – _Source-to-destination delivery_

![Image](images/Pasted%20image%2020260901190228.png)

**Key Functions:**

|Function|Description|
|---|---|
|**Logical Addressing**|Adds logical addresses (IP addresses) of sender and receiver|
|**Routing**|Determines the best path for packets to reach their destination|

---

### Layer 4: Transport Layer

**Responsibility:** Delivery of a **message from one process to another** (end-to-end).

> **FIGURE 2.10 HERE** – _Transport layer_

![Image](images/Pasted%20image%2020260901190611.png)

> **FIGURE 2.11 HERE** – _Reliable process-to-process delivery of a message_

![Image](images/Pasted%20image%2020260901190713.png)

**Key Functions:**

|Function|Description|
|---|---|
|**Service-Point Addressing**|Uses port numbers to identify specific processes/applications|
|**Segmentation & Reassembly**|Divides messages into segments; adds sequence numbers for reassembly|
|**Connection Control**|Connectionless or connection-oriented|
|**Flow Control**|End-to-end flow control|
|**Error Control**|End-to-end error control|

---

### Layer 5: Session Layer

**Responsibility:** Dialog control and synchronization.

> **FIGURE 2.12 HERE** – _Session layer_

![Image](images/Pasted%20image%2020260901190819.png)

**Key Functions:**

|Function|Description|
|---|---|
|**Dialog Control**|Manages half-duplex or full-duplex communication|
|**Synchronization**|Adds checkpoints (synchronization points) to data streams|

---

### Layer 6: Presentation Layer

**Responsibility:** Translation, compression, and encryption.

> **FIGURE 2.13 HERE** – _Presentation layer_

![Image](images/Pasted%20image%2020260901190852.png)

**Key Functions:**

|Function|Description|
|---|---|
|**Translation**|Converts sender format → common format → receiver format|
|**Encryption**|Transforms original information to secure form; decryption reverses it|
|**Compression**|Reduces number of bits (critical for multimedia transmission)|

---

### Layer 7: Application Layer

**Responsibility:** Providing services to the user.

> **FIGURE 2.14 HERE** – _Application layer_

![Image](images/Pasted%20image%2020260901190932.png)

**Key Functions:**

|Function|Description|
|---|---|
|**Network Virtual Terminal**|Allows remote login to hosts|
|**File Transfer, Access & Management**|Enables file access on remote hosts|
|**Mail Services**|Email forwarding and storage|
|**Directory Services**|Provides distributed database access for global information|

---

### OSI Model Summary

> **FIGURE 2.15 HERE** – _Summary of layers_

![Image](images/Pasted%20image%2020260901191016.png)

|Layer #|Layer Name|Responsibility|
|---|---|---|
|7|Application|Provides services to the user|
|6|Presentation|Translation, encryption, compression|
|5|Session|Dialog control and synchronization|
|4|Transport|Process-to-process delivery|
|3|Network|Source-to-destination packet delivery|
|2|Data Link|Hop-to-hop frame delivery|
|1|Physical|Bit-by-bit transmission|

---

## 2.4 TCP/IP PROTOCOL SUITE

### OSI vs. TCP/IP

The **TCP/IP protocol suite** has 5 layers when compared to the OSI model:

> **FIGURE 2.16 HERE** – _TCP/IP and OSI model_

![Image](images/Pasted%20image%2020260901191122.png)

|OSI Layer|TCP/IP Layer|
|---|---|
|Application|Application|
|Presentation|(Part of Application)|
|Session|(Part of Application)|
|Transport|Transport|
|Network|Network (Internet)|
|Data Link|Data Link|
|Physical|Physical|

---

### Network Layer (Internet Layer) — IP & Supporting Protocols

**Internet Protocol (IP)**

- **Unreliable** – no guaranteed delivery
    
- **Connectionless** – no session established beforehand
    
- **Best-Effort Delivery** – tries but makes no promises
    
- Transports data in packets called **datagrams**
    

**Supporting Protocols:**

|Protocol|Full Name|Purpose|
|---|---|---|
|**ARP**|Address Resolution Protocol|Finds physical (MAC) address when IP address is known|
|**RARP**|Reverse ARP|Finds IP address when only physical address is known|
|**ICMP**|Internet Control Message Protocol|Error reporting and diagnostics (e.g., **ping**)|
|**IGMP**|Internet Group Message Protocol|Manages multicast group memberships (streaming, gaming)|

---

### Transport Layer — Protocols

|Protocol|Delivery|Connection|Best For|
|---|---|---|---|
|**UDP** (User Datagram Protocol)|Unreliable|Connectionless|Speed-critical: streaming, gaming, VoIP|
|**TCP** (Transmission Control Protocol)|Reliable|Connection-oriented|Integrity-critical: web browsing, email, file transfer|
|**SCTP** (Stream Control Transmission Protocol)|Reliable|Connection-oriented|Combines best of TCP & UDP; VoIP, telecom signaling|

---

## 2.5 ADDRESSING IN TCP/IP

### Four Levels of Addresses

 📌 Chapter 2 Summary — At a Glance

- **OSI Model** = 7 layers: Physical, Data Link, Network, Transport, Session, Presentation, Application
    
- Each layer has **specific responsibilities** and communicates with its **peer layer** on other devices
    
- **TCP/IP** = 5 layers: Physical, Data Link, Network, Transport, Application
    
- **IP** is unreliable, connectionless, best-effort; supported by ARP, RARP, ICMP, IGMP
    
- **UDP** = fast but unreliable; **TCP** = slower but reliable; **SCTP** = hybrid
    
- **4 address types:** Physical (MAC), Logical (IP), Port, Specific
    
- **Physical addresses** change hop-to-hop; **logical & port** stay the same end-to-end

|Address Type|Layer|Description|Example|
|---|---|---|---|
|**Physical (MAC)**|Data Link (Layer 2)|Unique hardware address on NIC|`00:1A:2B:3C:4D:5E`|
|**Logical (IP)**|Network (Layer 3)|Routable address across networks|IPv4: `192.168.1.1` / IPv6: `2001:0db8:...`|
|**Port**|Transport (Layer 4)|Identifies specific process/service|`80`|
