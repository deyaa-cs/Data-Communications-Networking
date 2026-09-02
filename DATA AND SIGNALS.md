#  DATA AND SIGNALS

---

## 3.1 ANALOG AND DIGITAL

### The Core Concept

To be transmitted, **data must be transformed into electromagnetic signals**.

---

### Data Types

|Type|Description|Characteristics|
|---|---|---|
|**Analog Data**|Continuous information|Takes on **continuous values** (e.g., sound waves, temperature)|
|**Digital Data**|Information with discrete states|Takes on **discrete values** (e.g., 0s and 1s, text)|

---

### Signal Types

|Signal Type|Description|Values|
|---|---|---|
|**Analog Signal**|Continuous waveform|Can have an **infinite** number of values in a range|
|**Digital Signal**|Discrete waveform|Can have only a **limited** number of values|

> **FIGURE 3.1 HERE** – _Comparison of analog and digital signals_

![Image](images/Pasted%20image%2020260902073748.png)

---

### 💡 Key Insight

In data communications, we commonly use:

- **Periodic analog signals** – for continuous transmission
    
- **Nonperiodic digital signals** – for discrete data transmission
    

---

## 3.2 PERIODIC ANALOG SIGNALS

### Simple vs. Composite

|Type|Description|Example|
|---|---|---|
|**Simple**|Cannot be decomposed into simpler signals|A **sine wave**|
|**Composite**|Composed of multiple sine waves|Complex waveforms|

---

### The Sine Wave

> **FIGURE 3.2 HERE** – _A sine wave_

![Image](images/Pasted%20image%2020260902073814.png)

**Key Characteristics:**

|Characteristic|Description|
|---|---|
|**Frequency**|Rate of change with respect to time. **High frequency** = rapid change; **Low frequency** = slow change|
|**Zero Frequency**|Signal does not change at all|
|**Infinite Frequency**|Signal changes instantaneously|

---

### Wavelength

> **FIGURE 3.6 HERE** – _Wavelength and period_

![Image](images/Pasted%20image%2020260902073840.png)

---

### Time Domain vs. Frequency Domain

|Domain|Representation|
|---|---|
|**Time Domain**|Signal shown as amplitude vs. time|
|**Frequency Domain**|Signal shown as amplitude vs. frequency|

> 💡 A complete sine wave in the time domain = **one single spike** in the frequency domain.

---

### Bandwidth

**Bandwidth** = The difference between the **highest** and **lowest** frequencies contained in a composite signal.

> **FIGURE 3.12 HERE** – _The bandwidth of periodic and nonperiodic composite signals_

![Image](images/Pasted%20image%2020260902073904.png)

---

### Example 3.10 — Calculating Bandwidth

**Problem:** A periodic signal is decomposed into five sine waves with frequencies of **100, 300, 500, 700, and 900 Hz**. What is its bandwidth? Assume all components have a maximum amplitude of 10 V.

**Solution:**

- Highest frequency (`fh`) = 900 Hz
    
- Lowest frequency (`fl`) = 100 Hz
    

**Bandwidth (`B`) = `fh - fl` = 900 - 100 = 800 Hz**

> **FIGURE 3.13 HERE** – _The bandwidth for Example 3.10 (five spikes at 100, 300, 500, 700, 900 Hz)_

![Image](images/Pasted%20image%2020260902073935.png)

---

### Example 3.11 — Finding Lowest Frequency

**Problem:** A periodic signal has a bandwidth of **20 Hz**. The highest frequency is **60 Hz**. What is the lowest frequency? Draw the spectrum if the signal contains all frequencies of the same amplitude.

**Solution:**

- Bandwidth (`B`) = 20 Hz
    
- Highest frequency (`fh`) = 60 Hz
    

**Lowest frequency (`fl`) = `fh - B` = 60 - 20 = 40 Hz**

> **FIGURE 3.14 HERE** – _The bandwidth for Example 3.11 (spikes at all integer frequencies from 40 to 60 Hz)_

![Image](images/Pasted%20image%2020260902073955.png)

---

## 3.3 DIGITAL SIGNALS

### Representing Digital Data

Information can be represented by a **digital signal**:

- A **1** can be encoded as a positive voltage
    
- A **0** can be encoded as zero voltage
    

> **FIGURE 3.16 HERE** – _Two digital signals: one with two signal levels and the other with four signal levels_

![Image](images/Pasted%20image%2020260902074029.png)

---

### Bit Rate vs. Bit Length

|Term|Definition|
|---|---|
|**Bit Rate**|Number of bits sent per second (bps)|
|**Bit Length**|Distance one bit occupies on the transmission medium|

---

### Digital Signal as a Composite Analog Signal

> 💡 A **digital signal** is a **composite analog signal** with an **infinite bandwidth**.

> **FIGURE 3.19 HERE** – _Bandwidths of two low-pass channels_

![Image](images/Pasted%20image%2020260902074057.png)

---

### Two Contexts of Bandwidth in Networking

|Context|Definition|Unit|
|---|---|---|
|**Bandwidth in Hertz (Hz)**|Range of frequencies in a composite signal OR range of frequencies a channel can pass|**Hz**|
|**Bandwidth in Bits per Second (bps)**|Speed of bit transmission in a channel or link|**bps**|

---

## 📌 Chapter 3 Summary — At a Glance

- **Analog data** = continuous; **Digital data** = discrete
    
- **Analog signals** have infinite values; **Digital signals** have limited values
    
- **Periodic analog signals**: Simple (sine wave) or Composite (multiple sine waves)
    
- **Frequency** = rate of change; **Bandwidth** = `fh - fl`
    
- **Digital signals** = composite analog signals with infinite bandwidth
    
- **Bandwidth** has **two meanings**:
    
    1. Range of frequencies (Hz)
        
    2. Speed of transmission (bps)
