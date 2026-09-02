
#  THE PHYSICAL LAYER — GUIDED & WIRELESS TRANSMISSION, TELEPHONE SYSTEM & CABLE TV

---

## 4.1 GUIDED TRANSMISSION DATA

### Overview

Guided transmission uses **physical media** to carry signals from sender to receiver.

---

### Magnetic Media

- Used for data storage and physical transfer of data (e.g., tapes, hard drives)
    
- Not typically used for real-time data communications
    

---

### Twisted Pair

**What is it?**

- Two insulated copper wires, typically **1 mm thick**
    
- Wires are twisted in a **helical form** (like DNA)
    

> **Why twist?** Two parallel wires act as an antenna and radiate signals. When twisted, the waves from each wire **cancel out**, so the wires radiate less.

**Key Characteristics:**

- Can run several kilometers without amplification
    
- For longer distances, **repeaters** are needed
    

**Types:**

> **FIGURE: (a) Category 3 UTP HERE**  

![Image](images/Pasted%20image%2020260902074544.png)

> **FIGURE: (b) Category 5 UTP HERE**

![Image](images/Pasted%20image%2020260902074600.png)

|Category|Use|
|---|---|
|**Cat 3 UTP**|Older networks, telephone (up to 10 Mbps)|
|**Cat 5 UTP**|Modern Ethernet (up to 100 Mbps to 1 Gbps)|

---

### Coaxial Cable

**What is it?**

- Central copper conductor surrounded by insulating material
    
- Braided outer conductor shields the inner conductor
    

> **FIGURE: A coaxial cable HERE**

![Image](images/Pasted%20image%2020260902074627.png)

**Advantages:**

- Better shielding than twisted pair
    
- Higher bandwidth
    
- Less susceptible to interference
    

---

### Fiber Optics

**How it works:**

- Light rays travel through silica (glass) fiber
    
- Uses **total internal reflection** to keep light trapped inside the core
    

> **FIGURE: (a) Three examples of a light ray from inside a silica fiber impinging on the air/silica boundary at different angles 
> FIGURE: (b) Light trapped by total internal reflection HERE 

![Image](images/Pasted%20image%2020260902074754.png)

**Fiber Cable Structure:**

> FIGURE: (a) Side view of a single fiber   
> **FIGURE: (b) End view of a sheath with three fibers HERE

![Image](images/Pasted%20image%2020260902074845.png)
  

**Fiber Optic Networks:**

> **FIGURE: A fiber optic ring with active repeaters HERE

![Image](images/Pasted%20image%2020260902074917.png)

Advantages of Fiber:

- Extremely high bandwidth
    
- Low signal loss
    
- Immune to electromagnetic interference
    
- Secure (difficult to tap)
    

---

## 4.2 WIRELESS TRANSMISSION

### The Electromagnetic Spectrum

> **FIGURE: The electromagnetic spectrum and its uses for communication HERE**

![Image](images/Pasted%20image%2020260902074950.png)

**Key Bands for Communication:**

|Band|Use|
|---|---|
|**Radio**|AM/FM broadcasting, mobile phones, TV|
|**Microwave**|Satellite, point-to-point links, Wi-Fi|
|**Infrared**|Short-range remote controls, IRDA|
|**Lightwave**|Laser communication, fiber optics|

---

### Radio Transmission

> **FIGURE: (a) In the VLF, LF, and MF bands, radio waves follow the curvature of the earth
> FIGURE: (b) In the HF band, they bounce off the ionosphere HERE

![Image](images/Pasted%20image%2020260902075406.png)

**Ground Waves (VLF, LF, MF):**

- Follow the curvature of the Earth
    
- Used for long-distance AM radio, marine navigation
    

**Sky Waves (HF):**

- Bounce off the ionosphere
    
- Used for international shortwave radio
    

---

### Microwave Transmission

- Line-of-sight communication
    
- Used for satellite and terrestrial point-to-point links
    
- Higher frequencies = higher data rates
    

---

### Infrared and Millimeter Waves

- Short-range communication
    
- Requires line-of-sight
    
- Used in remote controls, some wireless peripherals
    

---

### Lightwave Transmission

> **FIGURE: Convection currents can interfere with laser communication systems — a bidirectional system with two lasers HERE

![Image](images/Pasted%20image%2020260902075449.png)

**Characteristics:**

- Uses lasers for communication
    
- Highly directional
    
- Affected by weather and atmospheric conditions (convection currents, fog, rain)
    

---

## 4.3 COMMUNICATION SATELLITES

### Types of Satellites

> **FIGURE: Communication satellites and their properties — altitude, round-trip delay, and number needed for global coverage HERE**

![Image](images/Pasted%20image%2020260902075514.png)

|Type|Altitude|Round-Trip Delay|Coverage|
|---|---|---|---|
|**GEO** (Geostationary)|~35,786 km|~270 ms|3 satellites needed for global coverage|
|**MEO** (Medium-Earth Orbit)|~5,000–15,000 km|~100 ms|More satellites needed|
|**LEO** (Low-Earth Orbit)|~500–2,000 km|~10–50 ms|Many satellites needed (e.g., Iridium)|

---

### Geostationary Satellites (GEO)

- Orbit above the equator at 35,786 km
    
- Appear stationary from Earth's surface
    
- Used for TV broadcasting, weather monitoring
    
- **Disadvantage:** High delay (~270 ms round trip)
    

---

### Medium-Earth Orbit Satellites (MEO)

- Lower altitude than GEO
    
- Used for GPS, navigation systems
    
- Lower delay than GEO
    

---

### Low-Earth Orbit Satellites (LEO)

- Very low altitude (500–2,000 km)
    
- Low delay (~10–50 ms)
    
- Used for satellite phone systems (e.g., Iridium)
    
- Need **many satellites** for global coverage
    

> FIGURE: Iridium satellites from six necklaces around the earth 
> **FIGURE: 1,628 moving cells cover the earth HERE**

![Image](images/Pasted%20image%2020260902075548.png)

---

### Satellites vs. Fiber

|Factor|Satellites|Fiber|
|---|---|---|
|**Coverage**|Global|Limited to cable routes|
|**Latency**|High (especially GEO)|Very low|
|**Deployment Cost**|High|High|
|**Bandwidth**|Good|Excellent|
|**Weather Impact**|Affected by rain/fog|Not affected|

---

### VSAT (Very Small Aperture Terminal)

> **FIGURE: VSATs using a hub HERE**

![Image](images/Pasted%20image%2020260902075640.png)

- Small satellite dish antennas
    
- Used for satellite broadband, corporate networks
    
- Communication goes: **User → Satellite → Hub → Satellite → User**
    

---

## 4.4 PUBLIC SWITCHED TELEPHONE SYSTEM (PSTN)

### Overview

> **FIGURE: The PSTN (Public Switching Telephone Network) originally designed for voice transmission HERE**

**Key Insight:** PSTN was designed for **voice** transmission, not data. A cable between two computers can transfer data at **1000 Mbps**, while a dial-up line has a maximum data rate of only **56 kbps** — a factor of **~20,000** difference!

---

### Structure of the Telephone System

**History:**

- **Alexander Graham Bell** invented the telephone in **1876**
    
- Early telephones were sold in **pairs**
    
- To talk to *n* users, separate wires had to be established
    
- This led to a **wild jumble of wire** — not a successful model
    

**Evolution:**

> FIGURE: (a) Fully-interconnected network 
> **FIGURE: (b) Centralized switch 
> FIGURE: (c) Two-level hierarchy HERE

![Image](images/Pasted%20image%2020260902075900.png)

**By 1878:** Bell Telephone Company established a switching office in New Haven, Connecticut.

**Two-Level Hierarchy:**

- Long-distance calls required connection between two switching offices
    
- Wiring between offices enabled longer-distance communication
    

---

### Major Components of the Telephone System

|Component|Description|
|---|---|
|**Local Loops**|Analog twisted pairs going to houses and businesses|
|**Trunks**|Digital fiber optics connecting switching offices|
|**Switching Offices**|Where calls are moved from one trunk to another|

> **FIGURE: A typical circuit route for a medium-distance call HERE**

![Image](images/Pasted%20image%2020260902075943.png)

---

### The Local Loop: Modems, ADSL, and Wireless

> **FIGURE: The use of both analog and digital transmissions for a computer-to-computer call — conversion done by modems and codecs HERE**

![Image](images/Pasted%20image%2020260902080006.png)

---

#### Transmission Line Problems

|Problem|Description|
|---|---|
|**Attenuation**|Loss of energy as the signal propagates outward (measured in dB/km)|
|**Distortion**|Different Fourier components propagate at different speeds|
|**Noise**|Unwanted energy from sources other than the transmitter|
|**Crosstalk**|Inductive coupling between two wires that are close together|

---

#### Modems

> FIGURE: (a) A binary signal 
> **FIGURE: (b) Amplitude modulation 
> FIGURE: (c) Frequency modulation 
> FIGURE: (d) Phase modulation HERE**

![Image](images/Pasted%20image%2020260902080056.png)

**Modulation Techniques:**

|Technique|Description|
|---|---|
|**Amplitude Modulation (AM)**|Two different amplitudes represent 0 and 1|
|**Frequency Modulation (FM)**|Two different frequencies (tones) represent 0 and 1|
|**Phase Modulation (PM)**|Carrier wave is shifted (e.g., 0° or 180°)|

---

### Wireless Local Loops

> **FIGURE: Architecture of an LMDS system HERE**

![Image](images/Pasted%20image%2020260902080255.png)

- LMDS (Local Multipoint Distribution Service)
    
- Uses microwave frequencies for broadband access
    
- Alternative to wired local loops
    

---

## 4.5 MULTIPLEXING

### Frequency Division Multiplexing (FDM)

> **FIGURE: (a) The original bandwidths 
> FIGURE: (b) The bandwidths raised in frequency 
> FIGURE: (c) The multiplexed channel HERE**

![Image](images/Pasted%20image%2020260902080207.png)

**Concept:** Different signals are transmitted at different frequencies (frequency bands) simultaneously.

---

### Time Division Multiplexing (TDM)

> **FIGURE: Delta modulation HERE**  

![Image](images/Pasted%20image%2020260902080319.png)

> **FIGURE: Multiplexing T1 streams into higher carriers HERE**

![Image](images/Pasted%20image%2020260902080347.png)

**Concept:** Different signals take turns on the same channel, each for a fixed time slot.

---

## 4.6 SWITCHING

### Circuit Switching vs. Packet Switching

> **FIGURE: (a) Circuit switching 
> FIGURE: (b) Packet switching HERE

![Image](images/Pasted%20image%2020260902080403.png)

|Feature|Circuit Switching|Packet Switching|
|---|---|---|
|**Path**|Dedicated path established before transmission|No dedicated path; packets find their own way|
|**Resource Allocation**|Reserved for entire session|Shared among multiple users|
|**Delay**|Low once connected|Variable delay|
|**Efficiency**|Inefficient for bursty traffic|Efficient for bursty traffic|
|**Example**|Traditional telephone network|Internet|

---

## 4.7 THE MOBILE TELEPHONE SYSTEM

### Generations of Mobile Phones

|Generation|Key Features|
|---|---|
|**1G**|Analog voice only|
|**2G**|Digital voice|
|**3G**|Digital voice + data (multimedia, internet)|

---

### Advanced Mobile Phone System (AMPS)

> **FIGURE: (a) Frequencies are not reused in adjacent cells  
> FIGURE: (b) To add more users, smaller cells can be used HERE

![Image](images/Pasted%20image%2020260902080430.png)

**Channel Categories (832 channels):**

|Category|Direction|Purpose|
|---|---|---|
|**Control**|Base → Mobile|Manage the system|
|**Paging**|Base → Mobile|Alert users to incoming calls|
|**Access**|Bidirectional|Call setup and channel assignment|
|**Data**|Bidirectional|Voice, fax, or data|

---

### Third-Generation Mobile Phones (3G / IMT-2000)

**Basic Services:**

|Service|Description|
|---|---|
|**High-Quality Voice**|Crystal-clear voice transmission|
|**Messaging**|Replaces email, fax, SMS, chat|
|**Multimedia**|Music, videos, films, TV|
|**Internet Access**|Web surfing with multimedia|

---

## 4.8 CABLE TELEVISION

### Community Antenna Television (CATV)

> **FIGURE: An early cable television system HERE**

![Image](images/Pasted%20image%2020260902080504.png)

- Original cable TV systems
    
- Community antenna receives broadcast signals and distributes via cable
    

---

### Internet over Cable

> **FIGURE: Cable television HERE**  

![Image](images/Pasted%20image%2020260902080527.png)

> **FIGURE: The fixed telephone system HERE**

![Image](images/Pasted%20image%2020260902080543.png)

**Spectrum Allocation:**

- Different frequency bands are allocated for:
    
    - TV channels
        
    - Upstream data (user → internet)
        
    - Downstream data (internet → user)
        

---

### Cable Modems

- Allow high-speed internet access over cable TV infrastructure
    
- Share bandwidth among users in the same neighborhood
    

---

### ADSL vs. Cable

|Factor|ADSL|Cable|
|---|---|---|
|**Medium**|Telephone copper line|Cable TV coax|
|**Asymmetry**|Yes (faster down, slower up)|Yes|
|**Bandwidth**|Up to 24 Mbps|Up to 1 Gbps|
|**Shared**|Dedicated line|Shared among neighborhood|
|**Distance Limit**|~5 km|No strict distance limit|

---

## 📌 Chapter 4 Summary — At a Glance

- **Guided Transmission:** Twisted Pair, Coaxial Cable, Fiber Optics
    
- **Wireless Transmission:** Radio, Microwave, Infrared, Lightwave
    
- **Satellites:** GEO (high delay), MEO (navigation), LEO (low delay, many needed)
    
- **PSTN:** Originally for voice; local loops, trunks, switching offices
    
- **Modems:** AM, FM, PM techniques to convert digital to analog
    
- **Multiplexing:** FDM (frequency) and TDM (time) to share channels
    
- **Switching:** Circuit-switched (dedicated path) vs. Packet-switched (shared)
    
- **Mobile Phones:** 1G (analog) → 2G (digital) → 3G (digital + data)
    
- **Cable TV:** Evolved to provide internet via cable modems
