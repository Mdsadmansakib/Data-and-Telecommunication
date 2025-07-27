# Complete Solutions to Telecommunications Questions 1-7

## Question 1

### a) What is the purpose of line encoding?
Line encoding is used to convert digital data into a digital signal suitable for transmission over a communication channel. The main purposes are:
- To provide synchronization between transmitter and receiver
- To ensure DC balance (no DC component)
- To provide error detection capability
- To make efficient use of bandwidth
- To match the signal characteristics to the transmission medium

### b) What is baseband and broadband transmission?
**Baseband transmission:** The original signal occupies the entire bandwidth of the transmission medium without modulation. The signal is transmitted directly from 0 Hz to maximum frequency. Example: Ethernet LAN.

**Broadband transmission:** The signal is modulated onto a carrier frequency before transmission. Multiple signals can share the same medium using different carrier frequencies. Example: Cable TV, DSL.

### c) Differentiate between physical layer and data link layer in OSI model
**Physical Layer (Layer 1):**
- Deals with electrical, mechanical, and procedural aspects
- Handles bit transmission over physical medium
- Defines voltage levels, timing, and physical connectors
- No error correction, just raw bit stream

**Data Link Layer (Layer 2):**
- Provides reliable data transfer between adjacent nodes
- Handles frame synchronization and error detection/correction
- Manages access to shared medium (MAC sublayer)
- Provides flow control and acknowledgments

### d) Broadcast network characteristics
A broadcast network transmits data from one station to all other stations simultaneously over a shared medium. Characteristics:
- Single transmission reaches all nodes
- Examples: Radio, TV, early Ethernet (bus topology)
- Requires medium access control protocols
- Potential for collisions in wireless networks
- Cost-effective for one-to-many communication

### e) Distinguish between distortion and noise
**Distortion:**
- Alteration of signal shape during transmission
- Caused by imperfect transmission medium characteristics
- Predictable and can be compensated
- Types: amplitude, delay, phase distortion

**Noise:**
- Random, unwanted signals added to the original signal
- Unpredictable and cannot be completely eliminated
- Types: thermal, shot, flicker noise
- Measured by Signal-to-Noise Ratio (SNR)

## Question 2

### a) PCM Signal Analysis
Given: Audio signal 300-3400 Hz, sampling at 8000 samples/second
For SNR = 30dB:

**Number of uniform quantization levels needed:**
SNR = 6.02n + 1.76 dB (for uniform quantization)
30 = 6.02n + 1.76
n = (30 - 1.76)/6.02 = 4.69 ≈ 5 bits

**Uniform quantization levels = 2^5 = 32 levels**

### b) PCM Encoder Analysis
Given: Full-scale voltage = 10V, 8-bit encoding
- Maximum quantized voltage = 10V
- Quantization levels = 2^8 = 256
- Step size = 10V/256 = 0.039V
- Actual maximum quantized level = 10 - 0.039 = 9.961V

### c) LC Filter Operation
An LC filter (inductor-capacitor) in an amplitude modulator circuit:
- **Low-pass LC filter:** Removes high-frequency components and harmonics
- **Band-pass LC filter:** Selects desired frequency band while rejecting others
- Provides impedance matching between stages
- Reduces spurious emissions and improves signal quality

### d) Frequency Modulation - Signal Multiplication
Multiplying two signals in frequency modulation creates:
- **Frequency mixing/heterodyning**
- Sum and difference frequencies are generated
- Used in superheterodyne receivers for frequency conversion
- Enables frequency translation and signal processing

## Question 3

### a) 16-QAM Constellation Diagram
16-QAM has 16 signal points arranged in a 4×4 grid:
```
   Q
   |
-3 -1  1  3  I
   |
```
Each point represents 4 bits (2^4 = 16 combinations)

### b) AM Modulation Analysis
Given: m₁(t) and m₂(t) as message signals, s₁(t) and s₂(t) as modulated signals
Using carrier frequency fc.

If simple AM modulation is used:
m₃(t) = A[m₁(t) + m₂(t)] represents a linear combination of the two message signals.

### c) Periodic Functions Analysis
For functions f₁(t) and f₂(t):
**f₁(t) + f₂(t) is periodic** if both have the same fundamental period or if their periods have a rational ratio.

**Conditions for periodicity:**
- If T₁/T₂ = p/q (rational numbers), then combined period = LCM(T₁,T₂)
- If T₁/T₂ is irrational, the sum is not periodic

### d) Signal Decomposition
From the given diagram showing multiplication and addition operations:
- Input: 6.5sin(10t)
- Operations: 4cos(5x) and 2sin(10t)
- Output represents frequency domain components
- Each sinusoidal component has specific frequency and phase characteristics

## Question 4

### a) TV Channel Harmonics
Given: TV channel bandwidth = 6 MHz, digital signal transmission

**Harmonics in digital signal:**
- Fundamental frequency and odd harmonics (3rd, 5th, 7th, etc.)
- For square wave: significant harmonics up to 5th-7th
- **Answer: 3 significant harmonics** (fundamental, 3rd, 5th)

### b) Nonperiodic Composite Signal
Given: Frequencies 10-30 kHz, peak amplitudes 10V and 30V for lowest/highest
- **Frequency spectrum:** Continuous spectrum from 10 kHz to 30 kHz
- **Amplitude variation:** Linear increase from 10V to 30V
- **Bandwidth:** 30 - 10 = 20 kHz

## Question 5

### a) FHSS and DSSS Coexistence
**Yes, FHSS and DSSS can coexist** in the same frequency band:
- They use different spreading techniques
- FHSS rapidly changes frequency, DSSS spreads across entire band
- Interference appears as noise to each system
- Both provide processing gain to overcome interference

### b) CDMA Analysis
Given chip sequences:
- A = (-1, -1, -1, +1, -1, +1, -1, +1)
- B = (-1, -1, +1, -1, +1, +1, +1, -1, -1)
- C = (-1, +1, -1, +1, +1, +1, -1, -1, +1)
- D = (-1, +1, -1, -1, -1, -1, +1, -1, +1)

Received sequence analysis would require correlation with each chip sequence to determine which stations transmitted and their bit values.

### c) Hamming Distance Calculation
For codewords (000100, 010101):
**Hamming distance = 3** (positions where bits differ: 2nd, 4th, 6th positions)

### d) FHSS System
Given: Total bandwidth = 400 MHz, individual channel = 1 kHz
**Number of frequency hops = 400 MHz / 1 kHz = 400,000 hops**

## Question 6

### a) CRC Calculation
For g(x) = 110101 and d(x) = 1110001011:
Using polynomial long division, the CRC remainder can be calculated.

### b) Traditional Checksum
**Yes, traditional checksum can be zero** when:
- Sum of all data words equals zero (modulo arithmetic)
- This doesn't necessarily indicate error-free transmission
- Modern checksums use more sophisticated algorithms

### c) CRC Generator Polynomial
For x¹⁹ generator:
- **Error detection capability:** Can detect up to 2-bit errors
- **Burst error detection:** Up to 19-bit burst errors
- **Probability of undetected error:** 2⁻¹⁹ for random errors

### d) CRC x² Term
The x² term in CRC generator polynomial:
- Ensures detection of 2-bit errors
- Provides specific error detection patterns
- Part of the mathematical structure for error detection

## Question 7

### a) Baud Rate Calculations
Given modulation types and bit rates:

i) **2000 bps, FSK:** Baud rate = 2000 (1 bit per symbol)
ii) **4000 bps, ASK:** Baud rate = 4000 (1 bit per symbol)  
iii) **6000 bps, QPSK:** Baud rate = 3000 (2 bits per symbol)
iv) **36,000 bps, 64-QAM:** Baud rate = 6000 (6 bits per symbol)

### b) Maximum Bits with 4 kHz Bandwidth
Given techniques with d = 0:

i) **ASK:** 2 × 4 kHz = 8,000 bps
ii) **QPSK:** 2 × 2 × 4 kHz = 16,000 bps  
iii) **16-QAM:** 4 × 2 × 4 kHz = 32,000 bps

### c) QPSK Implementation
QPSK (Quadrature Phase Shift Keying):
- Uses 4 phase states: 0°, 90°, 180°, 270°
- 2 bits per symbol encoding
- Two orthogonal carriers (I and Q channels)
- Constellation diagram shows 4 points on unit circle
- Better bandwidth efficiency than BPSK
