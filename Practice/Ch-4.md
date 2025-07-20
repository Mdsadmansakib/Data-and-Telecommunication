# Chapter 4 Digital Transmission - Complete Practice Set Solutions
**Reference:** Data Communications and Networking by Behrouz A. Forouzan

## 4.5.2 Questions

### Q4-1. List three techniques of digital-to-digital conversion.
1. **Line Coding** - Converting digital data to digital signals
2. **Block Coding** - Adding redundancy to improve performance
3. **Scrambling** - Replacing sequences that would create problems

### Q4-2. Distinguish between a signal element and a data element.
- **Data Element**: The smallest entity that can represent a piece of information (bit)
- **Signal Element**: The shortest unit (timewise) of a digital signal that carries data information

### Q4-3. Distinguish between data rate and signal rate.
- **Data Rate (N)**: Number of data elements (bits) sent in 1 second (bps)
- **Signal Rate (S)**: Number of signal elements sent in 1 second (baud)
- Relationship: S = N × (1/r) where r = log₂L (L = number of data levels)

### Q4-4. Define baseline wandering and its effect on digital transmission.
**Baseline Wandering**: The receiver averages the received signal power to determine signal baseline. Long strings of 0s or 1s cause the baseline to drift (wander), making it difficult to distinguish between 0s and 1s at the receiver.

**Effects:**
- Difficulty in signal interpretation
- Increased bit error rate
- Need for DC balancing

### Q4-5. Define a DC component and its effect on digital transmission.
**DC Component**: The average amplitude of a signal. When a digital signal has unequal numbers of positive and negative voltage levels, it creates a DC component.

**Effects:**
- Cannot pass through transformer-coupled systems
- Causes baseline wandering
- Creates electromagnetic interference
- Requires AC coupling which may distort signal

### Q4-6. Define the characteristics of a self-synchronizing signal.
**Self-Synchronizing Signal** characteristics:
- Contains timing information within the signal itself
- Has frequent signal transitions
- Allows receiver to recover clock from the received signal
- Maintains synchronization between sender and receiver
- Examples: Manchester, Differential Manchester

### Q4-7. List five line coding schemes discussed in this book.
1. **NRZ-L** (Non-Return-to-Zero Level)
2. **NRZ-I** (Non-Return-to-Zero Inverted)
3. **Manchester** (Biphase-L)
4. **Differential Manchester** (Biphase-M)
5. **AMI** (Alternate Mark Inversion)

### Q4-8. Define block coding and give its purpose.
**Block Coding**: A technique that converts a block of m bits to a block of n bits (n > m).

**Purposes:**
- Error detection and correction
- Ensuring adequate signal transitions for synchronization
- DC balancing
- Bandwidth efficiency improvement
- Examples: 4B/5B, 8B/10B

### Q4-9. Define scrambling and give its purpose.
**Scrambling**: A technique that replaces sequences of bits that would create problems for the line coding scheme with better sequences without increasing the number of bits.

**Purposes:**
- Eliminate long sequences of 0s
- Maintain synchronization
- Provide error detection capability
- Examples: B8ZS, HDB3

### Q4-10. Compare and contrast PCM and DM.
| Aspect | PCM (Pulse Code Modulation) | DM (Delta Modulation) |
|--------|-----------------------------|-----------------------|
| **Encoding** | Encodes amplitude of sample | Encodes difference between samples |
| **Bits per sample** | Multiple bits (n-bit quantization) | Single bit |
| **Complexity** | More complex | Simpler |
| **Bandwidth** | Higher bandwidth requirement | Lower bandwidth |
| **Quality** | Higher quality | Lower quality |
| **Applications** | High-quality audio/video | Voice transmission |

### Q4-11. What are the differences between parallel and serial transmission?
| Aspect | Parallel Transmission | Serial Transmission |
|--------|----------------------|-------------------- |
| **Data path** | Multiple wires (one per bit) | Single wire |
| **Speed** | Faster for short distances | Slower but more reliable |
| **Cost** | More expensive | Less expensive |
| **Distance** | Limited distance | Longer distances |
| **Skew problem** | Susceptible to skew | No skew problem |
| **Applications** | Internal computer buses | Network communications |

### Q4-12. List three different techniques in serial transmission and explain the differences.
1. **Asynchronous Transmission**:
   - No shared clock between sender and receiver
   - Uses start and stop bits
   - Character-by-character transmission
   - Simple but lower efficiency

2. **Synchronous Transmission**:
   - Shared clock between sender and receiver
   - Continuous stream of bits
   - Higher efficiency
   - More complex synchronization

3. **Isochronous Transmission**:
   - Combines features of both
   - Guaranteed data rate
   - Used for real-time applications
   - Constant time intervals between frames

## 4.5.3 Problems

### P4-1. Calculate the signal rate for each case in Figure 4.2 if data rate is 1 Mbps and c = 1/2.
**Formula**: S = c × N × (1/r)
- Given: N = 1 Mbps, c = 1/2
- For different schemes, r varies based on bits per signal element
- **Result**: S = 0.5 × 1 × (1/r) = 0.5/r Mbaud

### P4-2. Clock difference problem.
**Given**: Sender clock 0.2% faster than receiver, data rate = 1 Mbps
**Solution**: 
- Extra bits = 1,000,000 × 0.002 = **2,000 bits per second**

### P4-3. NRZ-L scheme analysis.
For NRZ-L:
- **a. 00000000**: No signal changes, bandwidth ≈ 0
- **b. 11111111**: No signal changes, bandwidth ≈ 0
- **c. 01010101**: Maximum changes, bandwidth = N/2 = 0.5 MHz
- **d. 00110011**: Moderate changes, bandwidth ≈ N/4 = 0.25 MHz

### P4-4. NRZ-I scheme analysis.
For NRZ-I (transition for 1, no transition for 0):
- **a. 00000000**: No transitions, bandwidth ≈ 0
- **b. 11111111**: All transitions, bandwidth = N/2 = 0.5 MHz
- **c. 01010101**: Irregular pattern
- **d. 00110011**: Some transitions

### P4-5. Manchester scheme analysis.
For Manchester (always one transition per bit):
- All cases have bandwidth = N = 1 MHz (due to guaranteed transitions)

### P4-6. Differential Manchester scheme analysis.
For Differential Manchester:
- All cases have bandwidth = N = 1 MHz (due to mid-bit transitions)

### P4-7. 2B1Q scheme analysis.
2B1Q uses 4 signal levels for 2 bits:
- **Signal rate** = N/2 = 0.5 Mbaud for all cases
- **Bandwidth** ≈ 0.25 MHz

### P4-8. MLT-3 scheme analysis.
MLT-3 uses three levels with specific transition rules:
- **Bandwidth** varies based on transition frequency
- Generally lower than Manchester schemes

### P4-9. Find 8-bit data stream from Figure 4.36.

![Figure 4.36 - Problem P4-9](https://github.com/Mdsadmansakib/Data-and-Telecommunication/blob/main/Practice/assets/4.36.png)

**Analysis of each waveform:**

**a. NRZ-I (Non-Return-to-Zero Inverted)**
- **Rule**: Binary 1 = signal level changes at bit boundary, Binary 0 = no change
- **Analysis**: Looking at signal transitions at each bit period:
  - Bit 1: High to Low transition → **1**
  - Bit 2: Stays Low → **0** 
  - Bit 3: Low to High transition → **1**
  - Bit 4: Stays High → **0**
  - Bit 5: High to Low transition → **1**
  - Bit 6: Stays Low → **0**
  - Bit 7: Low to High transition → **1**
  - Bit 8: Stays High → **0**
- **Answer: 10101010**

**b. Differential Manchester**
- **Rule**: Binary 0 = transition at beginning of bit period, Binary 1 = no transition at beginning
- **Analysis**: Looking at transitions at the start of each bit period:
  - Bit 1: Transition at start → **0**
  - Bit 2: No transition at start → **1**
  - Bit 3: Transition at start → **0**
  - Bit 4: No transition at start → **1**
  - Bit 5: Transition at start → **0**
  - Bit 6: No transition at start → **1**
  - Bit 7: Transition at start → **0**
  - Bit 8: No transition at start → **1**
- **Answer: 01010101**

**c. AMI (Alternate Mark Inversion)**
- **Rule**: Binary 0 = zero voltage, Binary 1 = alternating positive/negative voltage
- **Analysis**: Looking at signal levels during each bit period:
  - Bit 1: Positive pulse → **1**
  - Bit 2: Zero level → **0**
  - Bit 3: Negative pulse → **1**
  - Bit 4: Zero level → **0**
  - Bit 5: Positive pulse → **1**
  - Bit 6: Zero level → **0**
  - Bit 7: Negative pulse → **1**
  - Bit 8: Zero level → **0**
- **Answer: 10101010**

**Summary:**
| Line Coding Scheme | 8-bit Data Stream |
|-------------------|-------------------|
| NRZ-I             | **10101010**      |
| Differential Manchester | **01010101** |
| AMI               | **10101010**      |

### P4-10. NRZ-I normalized energy calculation.
Using power spectral density formulas for NRZ-I at 100 Kbps:
- **At 0 Hz**: P = 1.0
- **At 50 KHz**: P ≈ 0.64
- **At 100 KHz**: P = 0

### P4-11. Manchester normalized energy calculation.
For Manchester at 100 Kbps:
- **At 0 Hz**: P = 0 (no DC component)
- **At 50 KHz**: P ≈ 0.64
- **At 100 KHz**: P ≈ 0.04

### P4-12. 4B/5B block encoding.
*Note: Input stream not provided in the question*
**Process**: Each 4-bit group maps to specific 5-bit code to ensure sufficient transitions.

### P4-13. Invalid code sequences.
**5B/6B encoding**: 2⁶ - 2⁵ = 64 - 32 = **32 invalid sequences**
**3B/4B encoding**: 2⁴ - 2³ = 16 - 8 = **8 invalid sequences**

### P4-14. Scrambling sequence 11100000000000.
**a. B8ZS**: Replace 8 consecutive zeros with 000VB0VB pattern
- **Result**: 111000VB0VB000000

**b. HDB3**: Replace 4 consecutive zeros with B00V or 000V pattern
- **Result**: 1110000V0000V00V

### P4-15. Nyquist sampling rate.
**a. Low-pass signal (200 KHz BW)**: fs = 2 × 200 = **400 KHz**
**b. Band-pass signal (200 KHz BW, lowest freq 100 KHz)**: fs = 2 × 200 = **400 KHz**

### P4-16. PCM signal analysis (200 KHz BW, 1024 quantization levels).
**a. Bit rate**: N = 2 × 200 × log₂(1024) = 400 × 10 = **4 Mbps**
**b. SNRdB**: SNRdB = 6.02 × 10 + 1.76 = **61.96 dB**
**c. PCM bandwidth**: BW = N/2 = 4/2 = **2 MHz**

### P4-17. Maximum data rate (200 KHz BW, 4 levels).
Using Nyquist theorem: N = 2 × B × log₂(L) = 2 × 200 × log₂(4) = 2 × 200 × 2 = **800 Kbps**

### P4-18. SNR calculation (20 KHz analog BW, 30 Kbps channel).
**Sampling rate**: fs = 2 × 20 = 40 KHz
**Bits per sample**: n = 30,000/40,000 = 0.75 bits (not realistic)
*Note: This scenario is problematic as it requires less than 1 bit per sample*

### P4-19. Data rate for 1-MHz baseband channel.
**a. NRZ-L**: Data rate = Bandwidth = **1 Mbps**
**b. Manchester**: Data rate = Bandwidth/2 = **0.5 Mbps**
**c. MLT-3**: Data rate ≈ Bandwidth = **1 Mbps**

### P4-20. Transmission of 1000 characters (8 bits each).
**Total data**: 1000 × 8 = 8000 bits

**a. Synchronous transmission**: 
- Overhead: Frame headers, trailers
- **Transmitted bits**: ≈ 8000 + overhead (typically 8040-8080 bits)

**b. Asynchronous transmission**:
- Each character: 1 start + 8 data + 1 stop = 10 bits
- **Transmitted bits**: 1000 × 10 = **10,000 bits**

**c. Redundancy percentages**:
- **Synchronous**: ≈ 0.5-1%
- **Asynchronous**: (10,000-8000)/8000 × 100% = **25%**
