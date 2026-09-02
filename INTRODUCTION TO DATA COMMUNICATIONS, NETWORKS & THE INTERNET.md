
#  INTRODUCTION TO DATA COMMUNICATIONS, NETWORKS & THE INTERNET

---

## 1.1 DATA COMMUNICATIONS    

### What is Data Communications?

**Telecommunication** means communication at a distance.  
**Data** refers to information presented in whatever form is agreed upon by the parties creating and using it.

**Data communications** = the exchange of data between two devices via some form of transmission medium (e.g., wire cables).

---

### The 3 Pillars of an Effective Data Communications System

|Criterion|Description|
|---|---|
|**Delivery**|Data must reach the correct destination — the intended device or user.|
|**Accuracy**|Data must be delivered **without errors**.|
|**Timeliness**|Data must be delivered **without significant delay**. This is critical for real-time audio and video transmission. Also, packets must arrive in the **same order** they were sent — no **jitter** (variation in packet arrival time).|

---

### The 5 Components of Data Communication

|Component|Description|Example|
|---|---|---|
|**Message**|The information to be communicated|Text, numbers, pictures, audio, video|
|**Sender**|Device that sends the message|Computer, workstation, video camera|
|**Receiver**|Device that receives the message|Computer, workstation, telephone handset|
|**Transmission Medium**|The physical path for the message|Twisted-pair wire, coaxial cable, satellite|
|**Protocol**|The set of rules that govern communication|TCP/IP, HTTP, etc.|

> **FIGURE 1.1 HERE** – _Five components of data communication_  
   
![[Pasted image 20260901150304.png]]

---

### Data Flow Modes

|Mode|Direction|Example|
|---|---|---|
|**Simplex**|Unidirectional (one way only)|Keyboard to monitor|
|**Half-Duplex**|Both ways, but **one at a time**|Walkie-talkies|
|**Full-Duplex**|Both ways **simultaneously**|Telephone network|

> **FIGURE 1.2 HERE** – _Data flow (simplex, half-duplex, and full-duplex)_

![[Pasted image 20260901150405.png]]
---

## 1.2 NETWORKS

### What is a Network?

A **network** is a set of devices (called **nodes**) connected by communication **links**.  
Nodes can be computers, printers, or any device capable of sending/receiving data.

Most networks use **distributed computing** — a task is divided among multiple computers.

---

### Network Criteria

#### 1. Performance

Measured by:

- **Transit time** – time for a message to travel from one device to another.
    
- **Response time** – elapsed time between an inquiry and a response.
    

Performance depends on:

- Number of users
    
- Type of transmission medium
    
- Hardware capability
    
- Software efficiency
    
- **Throughput** and **delay**
    

#### 2. Reliability

Measured by:

- Frequency of failure
    
- Time to recover from failure
    
- Network robustness in catastrophes
    

#### 3. Security

Involves:

- Protecting data from unauthorized access
    
- Protecting data from damage
    
- Policies for recovery from breaches and data loss
    

---

### Types of Connection

|Type|Description|
|---|---|
|**Point-to-Point**|Dedicated link between **two** devices. Entire capacity is reserved for them.|
|**Multipoint (Multidrop)**|More than **two** devices share a single link. Can be spatially or time-shared.|

> **FIGURE 1.3 HERE** – _Types of connections: point-to-point and multipoint_ 

![[Pasted image 20260901150500.png]]

---

### Network Topologies

#### Mesh Topology

- Every device has a **dedicated point-to-point link** to every other device.
    
- **Number of links**:
    
    - Simplex: `n(n-1)`
        
    - Duplex: `n(n-1) / 2`
        
- Used in telephone regional offices.
    

> **FIGURE 1.5 HERE** – _Fully connected mesh topology (five devices)  

 
 _ 
![[Pasted image 20260901150656.png]]

#### Star Topology

- Each device has a dedicated link to a **central controller (hub)**.
    
- Commonly used in LANs.
    

> **FIGURE 1.6 HERE** – _Star topology connecting four stations_ 

 ![[Pasted image 20260901150814.png]]

#### Bus Topology

- A **single long cable** connects all devices.
    
- Devices connect via **drop lines** and **taps**.
    

> **FIGURE 1.7 HERE** – _Bus topology connecting three stations_ 

 ![[Pasted image 20260901150948.png]]

#### Ring Topology

- Each device has a dedicated point-to-point connection with **only the two devices on either side**.
    
- Signal passes in **one direction** until it reaches its destination.
    

> **FIGURE 1.8 HERE** – _Ring topology connecting six stations_ 

 ![[Pasted image 20260901151042.png]]

#### Hybrid Topology

- A combination of topologies (e.g., a star backbone with bus networks).
    

> **FIGURE 1.9 HERE** – _Hybrid topology: a star backbone with three bus networks_ 

![[Pasted image 20260901151106.png]]

---

### Categories of Networks

|Type|Description|Speed / Range|
|---|---|---|
|**LAN (Local Area Network)**|Privately owned; links devices in a single office, building, or campus.|Up to a few km; 100–1000 Mbps|
|**WAN (Wide Area Network)**|Covers large geographic areas (country, continent, world). Includes **switched WAN** (connects end systems/routers) and **point-to-point WAN** (leased line to ISP).|X.25, Frame Relay, ATM|
|**MAN (Metropolitan Area Network)**|Size between LAN and WAN; covers a town or city (e.g., cable TV networks).|—|

> **FIGURE 1.10 HERE** – _An isolated LAN connecting 12 computers to a hub in a closet_

![[Pasted image 20260901162157.png]]

> **FIGURE 1.11 HERE** – _WANs: a switched WAN and a point-to-point WAN_

![[Pasted image 20260901162219.png]]

> **FIGURE 1.12 HERE** – _A heterogeneous network made of four WANs and two LANs_ 

![[Pasted image 20260901162241.png]]

---

## 1.3 THE INTERNET

### Definition

An **internet** (internetwork) = two or more networks that can communicate.  
The **Internet** = collaboration of hundreds of thousands of interconnected networks.

---

### A Brief History

- **ARPANET** – the first network. Started with 4 nodes (universities).
    
- Each computer connected to an **Interface Message Processor (IMP)**.
    
- IMPs communicated with each other and with their attached host.
    
- **Vint Cerf & Bob Kahn** developed **TCP** (Transmission Control Protocol) for end-to-end packet delivery.
    
- Later, TCP was split into:
    
    - **TCP** – handles segmentation, reassembly, error detection.
        
    - **IP** (Internet Protocol) – handles datagram routing.
        
- This became known as **TCP/IP** – the foundation of the modern Internet.
    

---

### Internet Service Providers (ISPs) – Hierarchical Structure

|Level|Description|
|---|---|
|**International ISPs**|Connect nations together.|
|**National ISPs**|Backbone networks (e.g., SprintLink). Connected via **NAPs** (Network Access Points) or **peering points** (up to 600 Mbps).|
|**Regional ISPs**|Smaller than national; connect to one or more national ISPs.|
|**Local ISPs**|Provide direct service to end users. Could be an Internet company, a corporation, or a university.|

> **FIGURE 1.13 HERE** – _Hierarchical organization of the Internet_ 

![[Pasted image 20260901162545.png]]

---

## 1.4 PROTOCOLS AND STANDARDS

### What is a Protocol?

A **protocol** is a set of rules that govern data communications.  
Entities must **agree** on a protocol to communicate effectively — they can't just send random data and expect to be understood.

---

### Key Elements of a Protocol

|Element|Description|
|---|---|
|**Syntax**|Structure/format of the data (e.g., first 8 bits = source address).|
|**Semantics**|Meaning of each section of bits. What action to take based on interpretation.|
|**Timing**|When data should be sent and how fast (e.g., matching sender/receiver speed).|

---

### Standards

#### Two Categories

|Type|Meaning|
|---|---|
|**De Facto**|Not approved by an official body but adopted through widespread use.|
|**De Jure**|Legislated by an officially recognized body.|

Standards are developed through cooperation of committees, forums, and regulatory agencies.

---

### Standards Creation Committees

- **ISO** – International Organization for Standardization
    
- **ITU-T** – International Telecommunication Union – Telecommunications sector
    
- **ANSI** – American National Standards Institute
    

### Forums

- Special-interest groups with representatives from corporations.
    
- Work with universities and users to test, evaluate, and standardize new technologies.
    

### Regulatory Agencies

- Government agencies (e.g., **FCC** in the US) that regulate communications technology (e.g., radio).
    

---

### How an Internet Standard is Born

1. **Internet Draft** – a working document with no official status; 6-month lifetime.
    
2. After review, it may be published as an **RFC (Request for Comments)**.
    
3. Each RFC is edited, assigned a number, and made publicly available.
    
4. It may become a standard after passing through **maturity levels**:
    
    - Proposed Standard → Draft Standard → Internet Standard
        

---

### Examples of Internet Standards

|Protocol|Purpose|
|---|---|
|**IP (IPv4 / IPv6)**|Addressing and routing data across the Internet|
|**TCP**|Reliable, connection-oriented data transmission|
|**UDP**|Fast, connectionless data transmission|
|**HTTP**|Powers the World Wide Web (web servers ↔ clients)|
|**SMTP**|Sending email across networks|

> _Internet Standards enable the Internet to be a universal, accessible, and evolving platform for communication and information exchange._

---

## 📌 Summary – Chapter 1 at a Glance

- **Data communications** = exchange of data via a transmission medium.
    
- **5 components**: Message, Sender, Receiver, Medium, Protocol.
    
- **Data flow**: Simplex, Half-Duplex, Full-Duplex.
    
- **Networks** connect nodes; evaluated by performance, reliability, security.
    
- **Topologies**: Mesh, Star, Bus, Ring, Hybrid.
    
- **Network types**: LAN, WAN, MAN.
    
- **Internet** = network of networks; history from ARPANET to TCP/IP.
    
- **ISPs** form a hierarchy (International → National → Regional → Local).
    
- **Protocols** define syntax, semantics, timing.
    
- **Standards** are de facto or de jure; created via committees, forums, regulators.
    
- **Internet standards** go from Draft → RFC → Proposed → Draft → Standard.
    

---

