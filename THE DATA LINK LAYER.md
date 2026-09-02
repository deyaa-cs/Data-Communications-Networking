
#  THE DATA LINK LAYER

---

## 5.1 DATA LINK LAYER DESIGN ISSUES

### Overview

The Data Link Layer sits between the **Physical Layer** and the **Network Layer**. It takes raw bits from the physical layer and organizes them into **frames** for reliable transmission.

---

### Three Main Functions of the Data Link Layer

|Function|Description|
|---|---|
|**1. Service Interface**|Provides a service interface to the Network Layer above it|
|**2. Error Control**|Deals with transmission errors|
|**3. Flow Control**|Regulates data flow so slow receivers aren't swamped by fast senders|

> **FIGURE: Relationship between packets and frames HERE**

![Image](images/Pasted%20image%2020260902081535.png)

---

### Services Provided to the Network Layer

> FIGURE: (a) Virtual communication  
> **FIGURE: (b) Actual communication HERE**

![Image](images/Pasted%20image%2020260902081717.png)

**Three Service Possibilities:**

|Service Type|Description|Example Use|
|---|---|---|
|**Unacknowledged Connectionless**|No acknowledgement for frames sent; no error recovery|Ethernet, real-time voice/video|
|**Acknowledged Connectionless**|Each frame is individually acknowledged; retransmission if lost|Unreliable channels (Wi-Fi / 802.11)|
|**Acknowledged Connection-Oriented**|Connection established before transfer; numbered frames; guaranteed delivery in order|Satellite links, long-distance circuits|

---

### Acknowledged Connection-Oriented Service — Three Phases

1. **Connection Establishment** – Both sides initialize variables and counters
    
2. **Frame Transmission** – One or more frames are transmitted
    
3. **Connection Release** – Free up variables, buffers, and resources
    

> **FIGURE: Placement of the data link protocol HERE**

![Image](images/Pasted%20image%2020260902081737.png)

---

## 5.2 FRAMING

### What is Framing?

Framing is the process of breaking a stream of bits into **manageable data units called frames**.

---

### Four Framing Methods

|Method|Description|Used In|
|---|---|---|
|**1. Byte Count**|Header field specifies number of bytes in frame|Rarely used alone|
|**2. Flag Bytes with Byte Stuffing**|Special flag bytes mark start/end; escape byte inserted before accidental flags|PPP|
|**3. Flag Bits with Bit Stuffing**|Special bit pattern marks start/end; 0 inserted after five consecutive 1s|HDLC, USB|
|**4. Physical Layer Coding Violations**|Reserved signals indicate frame boundaries|Some systems|

---

### Method 1: Byte Count

> FIGURE: (a) A character stream without errors 
> **FIGURE: (b) A character stream with one error HERE**

![Image](images/Pasted%20image%2020260902081801.png)

- Uses a field in the header to specify the number of bytes in the frame
    
- **Problem:** If the count is distorted, synchronization is lost
    
- Rarely used by itself
    

---

### Method 2: Flag Bytes with Byte Stuffing

> FIGURE: (a) A frame delimited by flag bytes 
> **FIGURE: (b) Four examples of byte sequences before and after stuffing HERE**

![Image](images/Pasted%20image%2020260902081819.png)

- Each frame starts and ends with a special **flag byte** (same byte for both)
    
- **Byte Stuffing:** Insert a special escape byte (ESC) before any accidental flag byte in the data
    
- Used in **PPP (Point-to-Point Protocol)**
    

---

### Method 3: Flag Bits with Bit Stuffing

> FIGURE: (a) The original data 
> FIGURE: (b) The data as they appear on the line 
> **FIGURE: (c) The data as they are stored in receiver's memory after destuffing HERE**

![Image](images/Pasted%20image%2020260902081839.png)

- Each frame starts and ends with the bit pattern **01111110** (0x7E)
    
- **Bit Stuffing:** Insert a **0** after **five consecutive 1s** in the data
    
- Used in **HDLC** and **USB**
    

---

### Method 4: Physical Layer Coding Violations

- Uses reserved signals to indicate start/end of frames
    
- No need to stuff data since reserved signals are easily identifiable
    

---

### 💡 Practical Note

Data link protocols often use a **combination** of these methods for safety. For example, **Ethernet** and **802.11** (Wi-Fi) use a well-defined pattern called a **preamble** at the start of frames.

---

## 5.3 ERROR DETECTION AND CORRECTION

### Types of Errors

|Error Type|Description|
|---|---|
|**Single Error**|One error in the block|
|**Burst Error**|Two or more errors in the block|
|**Erasure Channel**|Physical layer detects a lost bit and declares it "erased"|

---

### Key Terminology

|Term|Definition|
|---|---|
|**Block Code**|Check bits computed from data bits|
|**Systematic Code**|Data bits sent directly, along with check bits|
|**Linear Code**|Check bits computed as a linear function of data bits|
|**Codeword**|Data bits + check bits (`n = m + r`)|
|**Code Rate**|`m/n` — fraction of codeword carrying actual information|
|**Hamming Distance**|Number of bit positions in which two codewords differ|

---

### Error-Correcting Codes

> **FIGURE: Use of a Hamming code to correct burst errors HERE**

![Image](images/Pasted%20image%2020260902081908.png)

- Allows the receiver to **correct** errors without retransmission
    
- More overhead than error-detecting codes
    
- Used when retransmission is expensive or impossible
    

---

### Error-Detecting Codes

> **FIGURE: Calculation of the polynomial code checksum HERE**

![Image](images/Pasted%20image%2020260902081926.png)

- Allows the receiver to **detect** errors
    
- If error is detected, frame is discarded and retransmission is requested
    
- More efficient than error-correcting codes for most applications
    

---

## 5.4 ELEMENTARY DATA LINK PROTOCOLS

### Protocol Frame Structure

> A frame composed of four fields: kind, seq, ack, and info HERE

|Field|Purpose|
|---|---|
|**kind**|Tells whether the frame contains data|
|**seq**|Sequence number of the frame|
|**ack**|Acknowledgment number|
|**info**|Actual data payload|

---

### Protocol 1: A Utopian (Unrestricted) Simplex Protocol

**Assumptions (Unrealistic!):**

|Assumption|Reality?|
|---|---|
|Data transmitted in one direction only|Unrealistic|
|Both sides always ready|Unrealistic|
|Processing time is ignored|Unrealistic|
|Infinite buffer space|Unrealistic|
|Channel never damages or loses frames|Unrealistic|

> **⚠️ This protocol has NO flow control, NO error correction, and NO error detection.**

---

### Protocol 2: A Simplex Stop-and-Wait Protocol (Error-Free Channel)

**Problem:** Prevent sender from flooding the receiver (Flow Control)

**Solution:** Receiver provides feedback via **acknowledgements**

> **Stop-and-Wait:** Sender sends one frame and waits for an acknowledgement before proceeding.

- Requires a **half-duplex** physical channel
    

---

### Protocol 3: A Simplex Stop-and-Wait Protocol (Noisy Channel)

**New Problem:** The channel now makes errors.

**Solutions:**

|Solution|Purpose|
|---|---|
|**Checksum**|Receiver detects errors and discards damaged frames|
|**Timer**|Sender retransmits if no acknowledgement arrives|
|**Sequence Numbers**|Distinguish first-time frames from retransmissions|

> **ARQ (Automatic Repeat reQuest)** or **PAR (Positive Acknowledgement with Retransmission)**

---

## 5.5 SLIDING WINDOW PROTOCOLS

### Key Concepts

> FIGURE: A sliding window of size 1, with a 3-bit sequence number 
> FIGURE: (a) Initially 
> FIGURE: (b) After the first frame has been sent   
> FIGURE: (c) After the first frame has been received 
> **FIGURE: (d) After the first acknowledgement has been received HERE**

![Image](images/Pasted%20image%2020260902082055.png)

---

### Piggybacking

- Data transmitted in **both directions**
    
- Technique of **temporarily delaying** outgoing acknowledgements to attach them to the next outgoing data frame
    
- Saves bandwidth by reducing the number of separate acknowledgment frames
    

---

### Sending Window vs. Receiving Window

|Window|Maintained By|Purpose|
|---|---|---|
|**Sending Window**|Sender|Sequence numbers of frames permitted to send|
|**Receiving Window**|Receiver|Sequence numbers of frames permitted to receive|

---

### Protocol 4: A One-Bit Sliding Window Protocol

- Uses **stop-and-wait** with a sliding window of size 1
    
- Works with a 3-bit sequence number
    

**Potential Problem:** If both sides initiate communication simultaneously, frames cross, causing confusion.

> FIGURE: (a) Normal case 
> **FIGURE: (b) Abnormal case HERE**  
> _(Notation: (seq, ack, packet number); asterisk indicates where network layer accepts a packet)_

![Image](images/Pasted%20image%2020260902082116.png)

---

### Pipelining

> **Bandwidth-Delay Product (BD) = bandwidth (bps) × one-way transit time (s)**

**Key Formula:**

- Number of frames sent before blocking = **`w = 2BD + 1`**
    
- Link utilization ≤ **`w / (1 + 2BD)`**
    

---

### Error Handling with Pipelining — Two Approaches

|Approach|Description|
|---|---|
|**Go-Back-N**|Receiver discards all subsequent frames after an error; no acknowledgements for discarded frames|
|**Selective Repeat**|Bad frame discarded, but good frames received after it are accepted and buffered|

---

### Cumulative Acknowledgement

- When an acknowledgement comes in for frame `n`, frames `n-1`, `n-2`, etc., are also automatically acknowledged
    
- Reduces the number of acknowledgements needed
    

> FIGURE: Pipelining and error recovery — effect on an error when (a) Receiver's window size is 1  
> **FIGURE: (b) Receiver's window size is large HERE**

![Image](images/Pasted%20image%2020260902082146.png)

---

## 📌 Chapter 5 Summary — At a Glance

- **Data Link Layer** = provides service interface, error control, flow control
    
- **Three services:** Unacknowledged connectionless, Acknowledged connectionless, Acknowledged connection-oriented
    
- **Framing methods:** Byte count, Byte stuffing, Bit stuffing, Physical coding violations
    
- **Error types:** Single error, Burst error, Erasure channel
    
- **Hamming distance** = measure of error detection/correction capability
    
- **Elementary protocols:** Utopian (unrealistic), Stop-and-Wait (error-free), Stop-and-Wait (noisy channel)
    
- **ARQ/PAR** = Automatic Repeat reQuest / Positive Acknowledgement with Retransmission
    
- **Sliding Window:** Sending window + Receiving window; pipelining improves efficiency
    
- **Pipelining error recovery:** Go-Back-N (discard all) vs. Selective Repeat (buffer good frames)
    
- **Cumulative acknowledgement** = one ACK acknowledges multiple frames
