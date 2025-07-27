# Communication Systems Solutions - Questions 1-7

## Question 1

### a) What is the purpose of line encoding? (2 marks)
Line encoding converts digital data into digital signals suitable for transmission over a communication channel. Its main purposes are:
- To represent digital bits as electrical signals with specific voltage levels, pulse shapes, and timing
- To ensure proper synchronization between transmitter and receiver
- To provide error detection capabilities
- To optimize bandwidth usage and power efficiency

### b) Explain how the following encoding schemes ensure synchronization (3 marks)
1. **Manchester encoding**: Uses a transition in the middle of each bit period. A '1' is represented by a low-to-high transition, and '0' by a high-to-low transition. The guaranteed transition in every bit provides continuous clock recovery.

2. **Differential Manchester encoding**: Similar to Manchester but uses the presence or absence of a transition at the beginning of the bit period to represent data, while maintaining the mid-bit transition for timing. This provides both synchronization and differential encoding benefits.

3. **MLT-3 encoding**: Uses three voltage levels (+V, 0, -V) and changes levels only for '1' bits, staying at the same level for '0' bits. The level changes help maintain synchronization while reducing electromagnetic interference.

### c) MLT-3 encoding analysis (2 marks)
Given voltage levels: +V, 0, -V, 0, 0, +V, -V
Starting from 0V and following MLT-3 rules:
- '1' bits cause level transitions in sequence: 0→+V→0→-V→+V→0→-V→0
- '0' bits maintain the current level

The received signal sequence corresponds to: **1, 1, 0, 1, 0, 1, 1**

### d) Calculate the baud rate for given bit rate and modulation type (4 marks)
Baud rate = Bit rate / Number of bits per symbol

i) **2000 bps, FSK**: FSK typically uses 1 bit per symbol
   Baud rate = 2000 / 1 = **2000 baud**

ii) **4000 bps, ASK**: ASK typically uses 1 bit per symbol
    Baud rate = 4000 / 1 = **4000 baud**

iii) **6000 bps, QPSK**: QPSK uses 2 bits per symbol (4 phases)
     Baud rate = 6000 / 2 = **3000 baud**

iv) **36,000 bps, 64-QAM**: 64-QAM uses 6 bits per symbol (2^6 = 64 symbols)
    Baud rate = 36,000 / 6 = **6000 baud**

### e) Distinguish between attenuation, distortion and noise (3 marks)
- **Attenuation**: Reduction in signal amplitude/power as it travels through the medium. It's a uniform reduction affecting all frequency components equally.

- **Distortion**: Change in signal shape due to different frequency components being affected differently by the channel. Types include delay distortion and amplitude distortion.

- **Noise**: Unwanted random signals added to the original signal during transmission. Examples include thermal noise, crosstalk, and impulse noise.

## Question 2

### a) Audio signal analysis for PCM (3 marks)
Given: Audio signal 300Hz to 3kHz, SNR = 30dB, sampling rate = 8000 samples/second

i) **Number of quantization levels for SNR = 30dB**:
   SNR(dB) = 6.02n + 1.76 (where n = number of bits)
   30 = 6.02n + 1.76
   n = (30 - 1.76)/6.02 ≈ 4.7 ≈ 5 bits
   Number of levels = 2^5 = **32 levels**

ii) **Bit rate**: 
    Bit rate = Sampling rate × bits per sample
    Bit rate = 8000 × 5 = **40,000 bps**

### b) PCM encoder analysis (5 marks)
Given: Full-scale voltage = 10V, 8-bit uniform quantization, normalized step size = 1 - 2^-8

i) **Normalized step size**: 1 - 2^-8 = 1 - 1/256 = **255/256**

ii) **Actual step size**: 
    Step size = Full-scale voltage / Number of levels
    Step size = 10V / 256 = **0.0391V**

iii) **Digital maximum quantized level**: 
     Maximum level = Full-scale - step size = 10 - 0.0391 = **9.961V**

iv) **Normalized resolution**: 1/256 = **0.0039**

v) **Actual resolution**: **0.0391V**

### c) Speech signal bandwidth calculation (3 marks)
Given: Bandwidth = 4 kHz, PCM transmission

i) **Minimum sampling rate** (Nyquist rate): 
   fs ≥ 2 × fmax = 2 × 4000 = **8000 samples/second**

ii) **Bit rate for 12-bit quantization**:
    Bit rate = Sampling rate × bits per sample
    Bit rate = 8000 × 12 = **96,000 bps**

iii) **Maximum quantization error for step size 0.1V**:
    Maximum error = ±step size/2 = ±0.1/2 = **±0.05V**

### d) Companding techniques (2 marks)
Companding combines compression and expansion to improve SNR for small signals while maintaining dynamic range. It compresses the signal at the transmitter (reduces dynamic range) and expands it at the receiver, providing better quantization for weak signals.

### e) Need for digital to digital converters (1 mark)
Digital-to-digital converters are needed to change the format, encoding scheme, or electrical characteristics of digital signals to match different systems, protocols, or transmission media requirements.

## Question 3

### a) QPSK modulation and demodulation (4 marks)
**QPSK (Quadrature Phase Shift Keying)**:
- Uses 4 different phase shifts (0°, 90°, 180°, 270°) to represent 2 bits per symbol
- **Modulation**: Two bit streams (I and Q) modulate cosine and sine carriers respectively
- **Demodulation**: Uses coherent detection with two correlators/matched filters for cosine and sine components
- The received signal is multiplied by local oscillator signals and integrated to recover the original bits

### b) Linear modulation analysis (3 marks)
Given: m₁(t) and m₂(t) are message signals, s₁(t) and s₂(t) are modulated signals, carrier frequency fc

If m₃(t) = m₁(t) + m₂(t), then the corresponding modulated signal s₃(t) will be:
s₃(t) = s₁(t) + s₂(t)

This demonstrates the **linearity property** of linear modulation schemes, where the sum of modulated signals equals the modulated sum of the original signals.

### c) QAM system data rate calculation (3 marks)
Given: Bandwidth = 5 MHz, data rate = 20 Mbps, modulation changed from 16-QAM to 64-QAM

- 16-QAM uses 4 bits per symbol
- 64-QAM uses 6 bits per symbol

Current symbol rate = 20 Mbps / 4 bits = 5 Msymbols/sec
New data rate with 64-QAM = 5 Msymbols/sec × 6 bits = **30 Mbps**

### d) Signal decomposition in frequency domain (4 marks)
Given the block diagram with 0.5sin(10t) input:

The system appears to perform frequency translation/mixing. The output o(p) would be the frequency domain representation showing:
- Original signal components
- Mixed/translated frequency components
- The specific mathematical analysis requires the complete system transfer function

## Question 4

### a) Fourier transform of 50% duty cycle square wave over period 2π (5 marks)
For a square wave with 50% duty cycle over period 2π:

X(ω) = (2A/π) × Σ[sin(nπ/2)/n] for odd n, where A is amplitude

The Fourier transform will have:
- Fundamental frequency component at ω₀ = 2π/(2π) = 1 rad/s
- Odd harmonics with decreasing amplitude
- Zero components at even harmonics

### b) AM circuit analysis (3 marks)
Given: A₀sin(2πfct) and A₀cos(2πfct) as carrier and modulating signals

When Ac becomes zero, the output will contain only the modulating signal component. The AM circuit will produce sidebands around the carrier frequency, and the demodulated output will represent the original modulating signal.

### c) AM radio transmitter analysis (3 marks)
Given: Voice signal 20Hz-3kHz, carrier 1000kHz, modulation index 0.6

**Sideband frequencies**: 
- Upper sideband: 1000kHz + (0.02-3)kHz = 1000.02-1003 kHz
- Lower sideband: 1000kHz - (0.02-3)kHz = 997-999.98 kHz

**Overall bandwidth**: 2 × 3kHz = **6 kHz**

### d) Diode-based amplitude modulator circuit (explanation required)
The LC block in a diode-based amplitude modulator typically serves as a tuned circuit for:
- Frequency selectivity
- Impedance matching
- Filtering unwanted harmonics
- Resonance at carrier frequency

## Question 5

### a) FHSS and DSSS co-existence (2 marks)
**Yes, FHSS and DSSS can co-exist** because:
- They use different spreading techniques
- FHSS uses frequency diversity while DSSS uses code diversity
- Interference between them is typically low due to processing gain
- Both systems can operate in the same frequency band with proper coordination

### b) CDMA analysis (5 marks)
Given chip sequences:
- A = (+1 +1 +1 +1, +1 +1 +1 +1)
- B = (+1 +1 -1 -1, +1 +1 -1 -1)
- C = (+1 +1 -1 -1 +1 +1 -1 -1)
- D = (+1 -1 +1 -1 +1 -1 +1 -1)
- E = (+1 -1 -1 +1 -1 +1 +1)

For codewords: (00000000, 11100000, 00011100, 10101010, 01010101)

**Analysis requires correlation calculations** between received signal and each chip sequence to determine which stations transmitted and their respective bits.

### c) Error correction analysis (5 marks)
Given: Total bandwidth W₈ = 400 MHz, individual channel bandwidth = 100 Hz

**Number of frequency hops**: 400 × 10⁶ / 100 = **4 × 10⁶ hops**

**PN bits required**: log₂(4 × 10⁶) ≈ **22 bits per frequency hop**

## Question 6

### a) Hamming distance definition (1 mark)
**Hamming distance** is the number of bit positions in which two codewords of equal length differ. It's a measure of the minimum number of single-bit errors needed to transform one codeword into another.

### b) Error detection and correction analysis (2 marks)
i) **Forward error detection**: Requires a minimum Hamming distance of **d+1** to detect d errors.

ii) **Forward error correction**: Requires a minimum Hamming distance of **2t+1** to correct t errors.

iii) **Error correction process**: Uses syndrome calculation and error pattern lookup tables to identify and correct error positions.

iv) **Overhead**: Forward error correction requires additional redundant bits, increasing transmission overhead but eliminating retransmission needs.

### c) CRC generator analysis (2 marks)
i) **Generator g(x) = 101**: Can detect **single-bit errors**
ii) **Generator g(x) = 101101**: Can detect **double-bit errors and some burst errors**

### d) CRC burst error detection (3 marks)
For generator 1100101, the probability of detecting a burst error of length depends on the generator polynomial degree. For most practical CRC generators, the probability of undetected burst errors is approximately **2^(-n)** where n is the degree of the generator polynomial.

## Question 7

### a) Flow control vs Error control (2 marks)
- **Flow control**: Manages the rate of data transmission between sender and receiver to prevent buffer overflow. Examples: Stop-and-Wait, Sliding Window
- **Error control**: Detects and corrects transmission errors. Examples: ARQ protocols, FEC

### b) Ethernet protocol analysis (3 marks)
In traditional Ethernet, when frames are corrupted, the receiving node discards them. This is an example of **Stop-and-Wait Protocol** because:
- Sender transmits one frame and waits for acknowledgment
- If corruption is detected, frame is discarded and timeout triggers retransmission
- Simple but inefficient due to waiting time

### c) Line encoding schemes (6 marks)
Given bit pattern: 0110100011001110110

**MLT-3**: Three levels (+V, 0, -V), changes level only for '1' bits
**NRZ-I**: Inverts signal for '1', maintains for '0'
**RZ**: Returns to zero in middle of bit period
**Differential Manchester**: Transition at bit boundary for data, mid-bit transition for timing
**Pseudo Ternary**: '0' represented by alternating +V/-V, '1' by 0V
**AMI**: '0' by 0V, '1' by alternating +V/-V

The actual waveforms would need to be drawn showing the specific voltage transitions for each encoding scheme.

### d) Piggybacking advantages (3 marks)
**Piggybacking** attaches acknowledgments to outgoing data frames instead of sending separate ACK frames.

**Advantages**:
- **Reduced overhead**: Eliminates separate ACK frames
- **Improved efficiency**: Better bandwidth utilization
- **Lower latency**: Faster acknowledgment delivery
- **Reduced network traffic**: Fewer total frames transmitted
