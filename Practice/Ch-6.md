# Chapter 6 Complete Solutions: Bandwidth Utilization - Multiplexing and Spectrum Spreading
*Reference: Data Communications and Networking by Behrouz A. Forouzan*

## 6.4.2 Questions

### Q6-1. Describe the goals of multiplexing.
**Answer:**
The goals of multiplexing are:
1. **Efficiency**: To achieve better bandwidth utilization by allowing multiple signals to share a single communication link
2. **Cost Reduction**: To reduce the cost per connection by sharing expensive transmission facilities among multiple users
3. **Resource Optimization**: To make maximum use of available bandwidth and transmission capacity
4. **Scalability**: To accommodate multiple users or data streams simultaneously over a single physical medium

### Q6-2. List three main multiplexing techniques mentioned in this chapter.
**Answer:**
The three main multiplexing techniques are:
1. **Frequency-Division Multiplexing (FDM)** - for analog signals
2. **Wavelength-Division Multiplexing (WDM)** - for optical signals
3. **Time-Division Multiplexing (TDM)** - for digital signals

### Q6-3. Distinguish between a link and a channel in multiplexing.
**Answer:**
- **Link**: Refers to the physical path or transmission medium (e.g., cable, fiber, wireless medium)
- **Channel**: Refers to the logical portion of a link that carries a single transmission or communication session

In multiplexing, multiple channels share the bandwidth of one physical link.

### Q6-4. Which of the three multiplexing techniques is (are) used to combine analog signals? Which is (are) used to combine digital signals?
**Answer:**
- **Analog signals**: 
  - Frequency-Division Multiplexing (FDM)
  - Wavelength-Division Multiplexing (WDM)
- **Digital signals**: 
  - Time-Division Multiplexing (TDM)

### Q6-5. Define the analog hierarchy used by telephone companies and list different levels of the hierarchy.
**Answer:**
The analog hierarchy is a standard system used by telephone companies to organize multiple voice channels into higher-level groups. The levels are:
1. **Group**: 12 voice channels (48 kHz bandwidth)
2. **Supergroup**: 5 groups = 60 voice channels (240 kHz bandwidth)
3. **Master Group**: 10 supergroups = 600 voice channels (2.52 MHz bandwidth)
4. **Jumbo Group**: 6 master groups = 3600 voice channels (16.984 MHz bandwidth)

### Q6-6. Define the digital hierarchy used by telephone companies and list different levels of the hierarchy.
**Answer:**
The digital hierarchy (also known as DS hierarchy) organizes digital channels:
1. **DS-0**: 64 kbps (basic voice channel)
2. **DS-1**: 1.544 Mbps (24 DS-0 channels + overhead) - T-1 line
3. **DS-2**: 6.312 Mbps (4 DS-1 channels + overhead)
4. **DS-3**: 44.736 Mbps (7 DS-2 channels + overhead) - T-3 line
5. **DS-4**: 274.176 Mbps (6 DS-3 channels + overhead)

### Q6-7. Which of the three multiplexing techniques is common for fiber-optic links? Explain the reason.
**Answer:**
**Wavelength-Division Multiplexing (WDM)** is most common for fiber-optic links.

**Reasons:**
- Fiber-optic cables have enormous bandwidth capacity that can accommodate multiple wavelengths
- Different wavelengths (colors) of light can travel simultaneously through the same fiber without interference
- WDM can dramatically increase the capacity of existing fiber infrastructure
- It's particularly effective for long-distance, high-capacity communications

### Q6-8. Distinguish between multilevel TDM, multiple-slot TDM, and pulse-stuffed TDM.
**Answer:**
- **Multilevel TDM**: Uses hierarchical approach where lower-rate streams are first multiplexed, then these multiplexed streams are further multiplexed at higher levels
- **Multiple-slot TDM**: Assigns multiple time slots to higher bit-rate sources within a single frame to accommodate sources with different data rates
- **Pulse-stuffed TDM**: Adds extra bits (stuffing bits) to synchronize sources with slightly different bit rates, ensuring all sources fit into a common frame structure

### Q6-9. Distinguish between synchronous and statistical TDM.
**Answer:**
- **Synchronous TDM**: 
  - Each input source has a dedicated time slot in every frame
  - Time slots are allocated whether the source has data to send or not
  - Fixed allocation regardless of activity
  - May waste bandwidth when sources are idle

- **Statistical TDM**: 
  - Time slots are dynamically allocated based on demand
  - Only active sources get time slots
  - Includes addressing information to identify sources
  - More efficient bandwidth utilization
  - Variable allocation based on activity

### Q6-10. Define spread spectrum and its goal. List the two spread spectrum techniques discussed in this chapter.
**Answer:**
**Spread Spectrum (SS)**: A technique that spreads a signal over a much wider bandwidth than the minimum required for transmission.

**Goals:**
- **Privacy**: Makes signals difficult to intercept and decode
- **Anti-jamming**: Provides resistance to interference and malicious jamming
- **Multiple access**: Allows multiple users to share the same frequency band

**Two techniques:**
1. **Frequency Hopping Spread Spectrum (FHSS)**
2. **Direct Sequence Spread Spectrum (DSSS)**

### Q6-11. Define FHSS and explain how it achieves bandwidth spreading.
**Answer:**
**Frequency Hopping Spread Spectrum (FHSS)**: A spread spectrum technique that rapidly switches the carrier frequency among many frequency channels using a pseudorandom sequence.

**How it achieves bandwidth spreading:**
- Uses M different carrier frequencies
- Signal hops from one frequency to another at regular intervals (hopping period)
- The hopping pattern is determined by a pseudorandom code
- The total bandwidth used is much larger than the bandwidth of the original signal
- Each hop uses only a small portion of the total spread bandwidth at any given time

### Q6-12. Define DSSS and explain how it achieves bandwidth spreading.
**Answer:**
**Direct Sequence Spread Spectrum (DSSS)**: A spread spectrum technique that multiplies the original data with a high-rate pseudorandom code sequence.

**How it achieves bandwidth spreading:**
- Each data bit is replaced by n bits using a spreading code (called chips)
- The spreading code has a much higher bit rate than the original data
- This multiplication spreads the signal over a much wider bandwidth
- The original signal can be recovered by multiplying with the same spreading code
- Common spreading codes include Barker sequences

## 6.4.3 Problems

### P6-1. Voice Channel Multiplexing with FDM
**Question:** Assume that a voice channel occupies a bandwidth of 4 kHz. We need to multiplex 10 voice channels with guard bands of 500 Hz using FDM. Calculate the required bandwidth.

**Solution:**
- Each voice channel: 4 kHz
- Guard band: 500 Hz
- Number of channels: 10
- Guard bands needed: 11 (9 between channels + 2 at edges)

Total bandwidth = (10 × 4 kHz) + (11 × 500 Hz)
Total bandwidth = 40 kHz + 5.5 kHz = **45.5 kHz**

### P6-2. Digitized Voice Channels Ratio
**Question:** We need to transmit 100 digitized voice channels using a passband channel of 20 KHz. What should be the ratio of bits/Hz if we use no guard band?

**Solution:**
- Standard digitized voice channel: 64 kbps (PCM)
- Total data rate = 100 × 64 kbps = 6.4 Mbps
- Available bandwidth = 20 kHz

Bits/Hz ratio = 6.4 × 10⁶ bps ÷ 20 × 10³ Hz = **320 bits/Hz**

### P6-3. Analog Hierarchy Overhead
**Question:** In the analog hierarchy of Figure 6.9, find the overhead (extra bandwidth for guard band or control) in each hierarchy level.

**Solution:**
Based on standard analog hierarchy:

**Group Level:**
- 12 voice channels × 4 kHz = 48 kHz
- Actual group bandwidth = 48 kHz
- Overhead = 48 - 48 = **0 kHz**

**Supergroup Level:**
- 5 groups × 48 kHz = 240 kHz (theoretical)
- Actual supergroup bandwidth = 240 kHz
- Overhead = 240 - 240 = **0 kHz**

**Master Group Level:**
- 10 supergroups × 240 kHz = 2400 kHz (theoretical)
- Actual master group bandwidth = 2520 kHz
- Overhead = 2520 - 2400 = **120 kHz**

**Jumbo Group Level:**
- 6 master groups × 2520 kHz = 15120 kHz (theoretical)
- Actual jumbo group bandwidth = 16984 kHz
- Overhead = 16984 - 15120 = **1864 kHz**

### P6-4. Synchronous TDM (1 bit per slot)
**Question:** Synchronous TDM combining 20 digital sources, each 100 Kbps. Each output slot carries 1 bit from each source, plus 1 synchronization bit per frame.

**Solution:**
a. **Frame size**: 20 sources × 1 bit + 1 sync bit = **21 bits**

b. **Frame rate**: Each source produces 100 kbps, so **100,000 frames/second**

c. **Frame duration**: 1 ÷ 100,000 = **10 μs**

d. **Output data rate**: 21 bits × 100,000 fps = **2.1 Mbps**

e. **Efficiency**: 20 useful bits ÷ 21 total bits = **95.24%**

### P6-5. Synchronous TDM (2 bits per slot)
**Question:** Repeat P6-4 if each output slot carries 2 bits from each source.

**Solution:**
a. **Frame size**: 20 sources × 2 bits + 1 sync bit = **41 bits**

b. **Frame rate**: 100,000 ÷ 2 = **50,000 frames/second**

c. **Frame duration**: 1 ÷ 50,000 = **20 μs**

d. **Output data rate**: 41 bits × 50,000 fps = **2.05 Mbps**

e. **Efficiency**: 40 useful bits ÷ 41 total bits = **97.56%**

### P6-6. Statistical TDM
**Question:** 14 sources, each creating 500 8-bit characters/second. Statistical TDM with 6 slots per frame, 4-bit addresses per slot.

**Solution:**
a. **Frame size**: 6 slots × (8 data bits + 4 address bits) = **72 bits**

b. **Frame rate**: Assuming full utilization, **500 frames/second**

c. **Frame duration**: 1 ÷ 500 = **2 ms**

d. **Output data rate**: 72 bits × 500 fps = **36 kbps**

### P6-7. Multilevel TDM
**Question:** Ten sources: six at 200 kbps, four at 400 kbps. Multilevel TDM, no sync bits.

**Solution:**
First, determine the lowest common multiple (LCM) for frame synchronization:
- LCM of 200 and 400 = 400 kbps

For a common frame rate, use 400 kHz:
- 200 kbps sources need 200,000 ÷ 400,000 = 0.5 bits per frame
- 400 kbps sources need 400,000 ÷ 400,000 = 1 bit per frame

To make whole numbers, use 800 kHz frame rate:
- 200 kbps sources: 1 bit per frame each
- 400 kbps sources: 2 bits per frame each

a. **Frame size**: (6 × 1) + (4 × 2) = **14 bits**

b. **Frame rate**: **800,000 frames/second**

c. **Frame duration**: 1 ÷ 800,000 = **1.25 μs**

d. **Data rate**: 14 bits × 800,000 fps = **11.2 Mbps**

### P6-8. Multiple-slot TDM
**Question:** Four channels: two at 200 kbps, two at 150 kbps. Multiple-slot TDM, no sync bits.

**Solution:**
Find LCM of 200 and 150 = 600

Using 600 kHz frame rate:
- 200 kbps channels get 200,000 ÷ 600,000 = 1/3 slot each
- 150 kbps channels get 150,000 ÷ 600,000 = 1/4 slot each

To get whole numbers, multiply by 12 (LCM of 3 and 4):
Frame rate = 600,000 × 12 = 7,200,000 fps

- 200 kbps channels: 4 slots each
- 150 kbps channels: 3 slots each

a. **Frame size**: (2 × 4) + (2 × 3) = **14 bits**

b. **Frame rate**: **7,200,000 frames/second**

c. **Frame duration**: 1 ÷ 7,200,000 = **0.139 μs**

d. **Data rate**: 14 bits × 7,200,000 fps = **100.8 Mbps**

### P6-9. Pulse-stuffing TDM
**Question:** Two channels: 190 kbps and 180 kbps. Pulse-stuffing TDM, no sync bits.

**Solution:**
For pulse stuffing, choose a common rate higher than both sources.
Let's use 200 kbps as the common rate.

Channel 1 (190 kbps): Needs stuffing rate = 200 - 190 = 10 kbps
Channel 2 (180 kbps): Needs stuffing rate = 200 - 180 = 20 kbps

a. **Frame size**: 2 bits (1 from each channel)

b. **Frame rate**: **200,000 frames/second**

c. **Frame duration**: 1 ÷ 200,000 = **5 μs**

d. **Data rate**: 2 bits × 200,000 fps = **400 kbps**

### P6-10. T-1 Line
**Question:** Answer questions about a T-1 line.

**Solution:**
T-1 specifications:
- 24 voice channels × 8 bits = 192 bits
- 1 framing bit per frame
- Frame size = 193 bits
- Data rate = 1.544 Mbps

a. **Frame duration**: 193 bits ÷ 1.544 × 10⁶ bps = **125 μs**

b. **Overhead**: 1 framing bit per frame
   Frame rate = 1.544 × 10⁶ ÷ 193 = 8000 fps
   Overhead = 8000 bits/second = **8 kbps**

### P6-11. Synchronous TDM Frame Contents
**Question:** Show contents of five output frames for synchronous TDM multiplexer combining four sources. Source 3 is silent.

Sources:
- Source 1: HELLO
- Source 2: HI  
- Source 3: (silent)
- Source 4: BYE

**Solution:**
Assuming 8-bit ASCII characters:

**Frame 1**: H(72), H(72), -, B(66)
**Frame 2**: E(69), I(73), -, Y(89)  
**Frame 3**: L(76), -, -, E(69)
**Frame 4**: L(76), -, -, -
**Frame 5**: O(79), -, -, -

Where "-" represents no data (could be NULL or padding).

### 🔢 **P6-12**  
**Problem:**  
A multiplexer in a synchronous TDM system takes 3-bit inputs and adds 1 framing bit. Each frame is 10 bits long. What is the output stream?

**Given Inputs:**  
Input 1: 10111011101
Input 2: 11111110000
Input 3: 10100000111

markdown
Copy
Edit

**Framing:** 1 framing bit per 3-bit sample (i.e., 3+1 = 4 bits per input)

**Frame structure (10 bits):** 3 bits from each input + 1 framing bit = 3×3 + 1 = 10

**Frame Construction:**  
Take 1 bit from each input in order repeatedly, then insert framing bits as necessary.

**Output Stream (Frame of 10 bits):**  
From arrows:
- Input 1 → `1 0 1`
- Input 2 → `1 1 1`
- Input 3 → `1 0 1`
- Framing bit → assumed last bit is for framing

**So Frame =** `1011111010` (1st bit from each, 2nd bit from each, 3rd bit from each, framing)

---

### 🔢 **P6-13**  
**Problem:**  
A demultiplexer receives a 16-bit frame. If there are no framing bits, what is the bit stream in each output?

**Input Stream (16 bits):**  
`10100000 10101010 11001100`

Group into 3 outputs:
- Round-robin demultiplexing: 1 bit to each line, repeatedly.

**Demultiplexed Outputs:**
- Output 1: 1 0 0 0 1 0 (bits 1, 4, 7, 10, 13, 16) = `100010`
- Output 2: 0 0 1 1 1 (bits 2, 5, 8, 11, 14) = `00111`
- Output 3: 1 0 0 0 0 (bits 3, 6, 9, 12, 15) = `10000`

---

### 🔢 **P6-14**  
**Problem:**  
What is the overhead (extra bits) in each level of the digital hierarchy?

Refer to Figure 6.23:

- **a. DS-1**:  
  - 24 DS-0 channels → 24 × 8 bits = 192 bits  
  - Total bits in DS-1: 193 bits (1 framing bit added)  
  - **Overhead = 193 - 192 = 1 bit**

- **b. DS-2:**  
  - 4 DS-1 channels → 4 × 193 = 772 bits  
  - Total bits in DS-2 = 772 + 4 (overhead bits) = 776 bits  
  - **Overhead = 4 bits**

- **c. DS-3:**  
  - 7 DS-2 channels → 7 × 776 = 5432 bits  
  - Actual DS-3 = 44.736 Mbps  
  - Payload = 6.312 × 7 = 44.184 Mbps  
  - **Overhead ≈ 44.736 - 44.184 = 0.552 Mbps**  
  - Overhead bits = 552,000 / 8000 = **69 bits/frame (approx.)**

- **d. DS-4:**  
  - 6 DS-3 channels → 6 × 44.736 = 268.416 Mbps  
  - Total DS-4 = 274.176 Mbps  
  - **Overhead = 274.176 - 268.416 = 5.76 Mbps**  
  - Overhead bits/frame = 5.76 Mbps / 8000 = **720 bits/frame (approx.)**

---

### 🔢 **P6-15**  
**Problem:**  
What is the number of bits in a PN sequence if using FHSS with:
- Bandwidth B = 8 kHz
- Bs = 100 kHz

**Answer:**  
For FHSS:  
- \( N = \frac{B_s}{B} = \frac{100\text{ kHz}}{8\text{ kHz}} = 12.5 \approx 13 \) channels  
- Number of bits needed to represent 13 channels = ⌈log₂(13)⌉ = **4 bits**

---

### 🔢 **P6-16**  
**FHSS system with 4-bit PN sequence, 64 bits/sec.**

- **a. Number of channels:**  
  - 4-bit PN sequence = \( 2^4 = 16 \) channels  
  - **Answer: 16 channels**

- **b. Time for full cycle:**  
  - Sequence length = \( 2^4 - 1 = 15 \) bits (for maximal-length PN)  
  - Bit rate = 64 bits/sec  
  - Time = \( 15 / 64 \) = **0.234375 seconds**

---

### 🔢 **P6-17**  
**Problem:**  
Given pseudo-random generator:  
\[
N_{i+1} = (5 + 7N_i) \mod 17
\]

**Initial seed:** Let \( N_0 = 1 \)

**Generating sequence:**
N0 = 1
N1 = (5 + 7×1) mod 17 = 12
N2 = (5 + 7×12) mod 17 = (5 + 84) mod 17 = 89 mod 17 = 4
N3 = (5 + 7×4) = 33 mod 17 = 16
N4 = (5 + 7×16) = 117 mod 17 = 15
N5 = (5 + 7×15) = 110 mod 17 = 8
N6 = (5 + 7×8) = 61 mod 17 = 10
N7 = (5 + 7×10) = 75 mod 17 = 7
...

yaml
Copy
Edit

**Sequence (first few values):** 1, 12, 4, 16, 15, 8, 10, 7, ...

---

### 🔢 **P6-18**  
**Problem:**  
Given:
- Data rate = 10 Mbps  
- Voice channel = 64 kbps  
- Using DSSS with Barker sequence (11 bits/chip)

**Processing Gain (Gp):**  
\[
Gp = \frac{\text{chip rate}}{\text{bit rate}} = 11
\]

**Bit rate per channel using DSSS =**  
\[
64 \text{ kbps } × 11 = 704 \text{ kbps per channel}
\]

**Max number of channels =**  
\[
\frac{10 \text{ Mbps}}{704 \text{ kbps}} ≈ 14.2 \Rightarrow \boxed{14 \text{ channels (max)}}
\]
