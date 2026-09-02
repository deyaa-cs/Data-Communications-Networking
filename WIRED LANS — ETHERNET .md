
# WIRED LANS — ETHERNET 

---

## 6.1 IEEE STANDARDS — PROJECT 802

### Overview

In **1985**, the Computer Society of the IEEE started **Project 802** to set standards enabling intercommunication among equipment from various manufacturers.

> **Project 802** specifies functions of the **Physical Layer** and **Data Link Layer** for major LAN protocols.

---

### IEEE 802 Working Groups

|Active Working Groups|Inactive/Disbanded|
|---|---|
|**802.1** — Higher Layer LAN Protocols|802.2 — Logical Link Control|
|**802.3** — Ethernet|802.4 — Token Bus|
|**802.11** — Wireless LAN (Wi-Fi)|802.5 — Token Ring|
|**802.15** — Wireless PAN (Bluetooth)|802.7 — Broadband Area Network|
|**802.16** — Broadband Wireless Access|802.8 — Fiber Optic TAG|
|**802.17** — Resilient Packet Ring|802.9 — Integrated Service LAN|
|**802.18** — Radio Regulatory TAG|802.10 — Security|
|**802.19** — Coexistence TAG|802.12 — Demand Priority|
|**802.20** — Mobile Broadband Wireless Access|802.14 — Cable Modem|
|**802.21** — Media Independent Handoff||
|**802.22** — Wireless Regional Area Networks||

---

### Logical Link Control (LLC)

- LLC defines a **Protocol Data Unit (PDU)** similar to HDLC
    
- Provides **flow and error control** for upper-layer protocols that demand these services
    
- Part of the Data Link Layer (above MAC)
    

---

## 6.2 STANDARD ETHERNET

### History

- Original Ethernet created in **1976** at **Xerox PARC** (Palo Alto Research Center)
    
- Has gone through **four generations** of evolution
    

---

### MAC Sublayer

**Frame Fields:**

|Field|Description|
|---|---|
|**Preamble**|Alerts the receiving system to the incoming frame; enables synchronization of input timing|
|**CRC**|Uses **CRC-32** for error detection|

---

### Addressing

> **FIGURE: Ethernet address in hexadecimal notation HERE**

![Image](images/Pasted%20image%2020260902083019.png)

**Address Types:**

|Bit|Type|Description|
|---|---|---|
|**LSB = 0**|**Unicast**|Address identifies a single device|
|**LSB = 1**|**Multicast**|Address identifies a group of devices|
|**All bits = 1**|**Broadcast**|Special case of multicast; sends to all devices|

---

### Access Method: CSMA/CD

- Uses **1-persistent CSMA/CD** (Carrier Sense Multiple Access with Collision Detection)
    

---

### Slot Time

**Slot Time = Round-trip time + Time to send jam sequence**

|Ethernet Type|Slot Time|
|---|---|
|**10 Mbps Ethernet**|**512 bits = 51.2 μs**|

---

### Maximum Network Length Calculation

**Formula:**

text

Max Length = Propagation Speed × (Slot Time / 2)

**Theoretical Calculation:**

text

Max Length = (2 × 10⁸) × (51.2 × 10⁻⁶ / 2) = 5,120 m

**Actual Standard:** **2,500 m** (≈48% of theoretical, accounting for delays in repeaters, interfaces, and jam sequence time)

---

### Physical Layer — Standard Ethernet

|Type|Name|Description|
|---|---|---|
|**10Base5**|Thick Ethernet|Thick coaxial cable, bus topology|
|**10Base2**|Thin Ethernet|Thin coaxial cable, bus topology|
|**10BaseT**|Twisted-Pair Ethernet|UTP cable, star topology|
|**10Base-F**|Fiber Ethernet|Fiber optic cable|

> **FIGURE: 10Base5 — Thick Ethernet HERE**

![Image](images/Pasted%20image%2020260902083111.png)

> **FIGURE: 10Base2 — Thin Ethernet HERE**  

![Image](images/Pasted%20image%2020260902083128.png)

> **FIGURE: 10BaseT — Twisted-Pair Ethernet HERE** 

![Image](images/Pasted%20image%2020260902083148.png)

> **FIGURE: 10Base-F — Fiber Ethernet HERE**

![Image](images/Pasted%20image%2020260902083205.png)

---

### Summary of Standard Ethernet

> **FIGURE: Summary of Standard Ethernet HERE**

![Image](images/Pasted%20image%2020260902083227.png)

|Feature|Specification|
|---|---|
|**Data Rate**|10 Mbps|
|**Access Method**|CSMA/CD|
|**Topology**|Bus (10Base5/2), Star (10BaseT/F)|
|**Media**|Coax, UTP, Fiber|
|**Max Length**|2,500 m|
|**Frame Size**|64–1,518 bytes|

---

## 6.3 CHANGES IN THE STANDARD

### Bridged Ethernet

> **FIGURE: Bridged Ethernet — raising bandwidth and separating collision domains HERE**

![Image](images/Pasted%20image%2020260902083311.png)

- Divides network into **collision domains**
    
- Each domain has its own bandwidth
    
- Collisions are **isolated** to each segment
    

---

### Switched Ethernet

> **FIGURE: Switched Ethernet — N-port bridge HERE**

![Image](images/Pasted%20image%2020260902083327.png)

- Uses a **switch** (N-port bridge)
    
- Each device gets a **dedicated** connection to the switch
    
- No collisions between devices
    
- Full bandwidth per device
    

---

### Full-Duplex (Switched) Ethernet

> **FIGURE: Full-duplex (switched) Ethernet — no need for CSMA/CD HERE**

![Image](images/Pasted%20image%2020260902083340.png)

- **No CSMA/CD needed** because:
    
    - Only **two devices** on the link
        
    - Simultaneous transmission in both directions
        
- Double the throughput potential
    

---

## 6.4 FAST ETHERNET (IEEE 802.3u)

### Key Features

|Feature|Description|
|---|---|
|**Data Rate**|100 Mbps (10× faster)|
|**Compatibility**|Same 48-bit address, same frame format, same min/max frame length|
|**Access Method**|CSMA/CD for half-duplex; **no CSMA/CD** for full-duplex|

---

### Autonegotiation

- Allows two devices to **negotiate** the mode (half/full) or data rate
    
- Ensures compatibility and optimal performance
    

---

### Fast Ethernet — Physical Layer

|Implementation|Media|Max Length|
|---|---|---|
|**100Base-TX**|2 pairs of Cat 5 UTP|100 m|
|**100Base-FX**|2 fibers (MMF)|2,000 m|
|**100Base-T4**|4 pairs of Cat 3 UTP|100 m|

> **FIGURE: Fast Ethernet — Topology HERE**  

![Image](images/Pasted%20image%2020260902083419.png)

> **FIGURE: Fast Ethernet — Implementation HERE**

![Image](images/Pasted%20image%2020260902083433.png)

---

### Encoding

|Type|Encoding|Description|
|---|---|---|
|**100Base-TX**|MLT-3 + 4B/5B|Uses 2 pairs|
|**100Base-FX**|NRZI + 4B/5B|Uses fiber|
|**100Base-T4**|8B/6T|Uses 4 pairs|

> **FIGURE: Fast Ethernet — Encoding HERE**

![Image](images/Pasted%20image%2020260902083450.png)

---

### Summary of Fast Ethernet

> **FIGURE: Summary of Fast Ethernet HERE**

![Image](images/Pasted%20image%2020260902083508.png)

|Feature|Specification|
|---|---|
|**Data Rate**|100 Mbps|
|**Access Method**|CSMA/CD (half) / None (full)|
|**Compatibility**|Full with Standard Ethernet|
|**Media**|Cat 5 UTP, Fiber|
|**Max Length**|100 m (UTP), 2,000 m (Fiber)|

---

## 6.5 GIGABIT ETHERNET (IEEE 802.3z)

### Key Features

|Feature|Description|
|---|---|
|**Data Rate**|1 Gbps (1,000 Mbps)|
|**Compatibility**|Same addresses, same frame format, same min/max frame length|
|**Autonegotiation**|Supported (as in Fast Ethernet)|

---

### MAC Sublayer

**Most implementations:** **Full-duplex** mode — **no collisions** → cable length limited only by attenuation

**Half-duplex mode (very rare):**

|Issue|Solution|
|---|---|
|**Traditional**|0.512 μs → max length = 25 m|
|**Carrier Extension**|Minimum frame length extended to **512 bytes (4,096 bits)**|
|**Frame Bursting**|Multiple frames sent together to improve efficiency|

---

### Gigabit Ethernet — Physical Layer

|Implementation|Media|Max Length|Encoding|
|---|---|---|---|
|**1000Base-SX**|MMF (short wavelength)|220–550 m|8B/10B|
|**1000Base-LX**|MMF/SMF (long wavelength)|550 m–5 km|8B/10B|
|**1000Base-CX**|Shielded copper|25 m|8B/10B|
|**1000Base-T**|4 pairs Cat 5 UTP|100 m|4D-PAM5|

> **FIGURE: Gigabit Ethernet — Topology HERE**  

![Image](images/Pasted%20image%2020260902083532.png)

> **FIGURE: Gigabit Ethernet — Implementation HERE**  

![Image](images/Pasted%20image%2020260902083548.png)

> **FIGURE: Gigabit Ethernet — Encoding HERE**


![Image](images/Pasted%20image%2020260902083602.png)

---

### Summary of Gigabit Ethernet

> **FIGURE: Summary of Gigabit Ethernet HERE**

![Image](images/Pasted%20image%2020260902083617.png)

|Feature|Specification|
|---|---|
|**Data Rate**|1 Gbps|
|**Access Method**|None (full-duplex) / CSMA/CD (half)|
|**Compatibility**|Full with Standard & Fast Ethernet|
|**Media**|MMF, SMF, Copper, Cat 5 UTP|
|**Max Length**|100 m (UTP), 5 km (SMF)|

---

## 6.6 TEN-GIGABIT ETHERNET (IEEE 802.3ae)

### Key Features

|Feature|Description|
|---|---|
|**Data Rate**|10 Gbps (10,000 Mbps)|
|**Compatibility**|Same addresses, same frame format, same min/max frame length|
|**Purpose**|Allows interconnection of LANs into MANs or WANs|
|**Compatibility**|Makes Ethernet compatible with Frame Relay and ATM|

---

### MAC Sublayer

- **Only in full-duplex mode**
    
- **No CSMA/CD** needed — no collisions possible
    

---

### Ten-Gigabit Ethernet Applications

|Use Case|Description|
|---|---|
|**MAN (Metropolitan Area Network)**|Connect LANs across a city|
|**WAN (Wide Area Network)**|Connect LANs across large geographic areas|
|**Backbone**|High-speed backbone for networks|

---

## 📌 Chapter 6 Summary — Ethernet Evolution

|Generation|Standard|Data Rate|Key Features|
|---|---|---|---|
|**Standard Ethernet**|IEEE 802.3|10 Mbps|CSMA/CD, 10Base5/2/T/F|
|**Fast Ethernet**|IEEE 802.3u|100 Mbps|Autonegotiation, full-duplex|
|**Gigabit Ethernet**|IEEE 802.3z|1 Gbps|Full-duplex, carrier extension (half)|
|**10-Gigabit Ethernet**|IEEE 802.3ae|10 Gbps|Full-duplex only, WAN/MAN capable|

---

### Evolution Path

text

10 Mbps (Standard)
    ↓
100 Mbps (Fast Ethernet)
    ↓
1,000 Mbps (Gigabit Ethernet)
    ↓
10,000 Mbps (10-Gigabit Ethernet)

---

### Ethernet Family Tree

| Type            | Media      | Max Length | Topology |
| --------------- | ---------- | ---------- | -------- |
| **10Base5**     | Thick Coax | 500 m      | Bus      |
| **10Base2**     | Thin Coax  | 185 m      | Bus      |
| **10BaseT**     | Cat 3 UTP  | 100 m      | Star     |
| **10Base-F**    | Fiber      | 2,000 m    | Star     |
| **100Base-TX**  | Cat 5 UTP  | 100 m      | Star     |
| **100Base-FX**  | MMF        | 2,000 m    | Star     |
| **1000Base-SX** | MMF        | 220–550 m  | Star     |
| **1000Base-LX** | MMF/SMF    | 550 m–5 km | Star     |
| **1000Base-T**  | Cat 5 UTP  | 100 m      | Star     |
