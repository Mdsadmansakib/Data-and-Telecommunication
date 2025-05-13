# Data Communications Mid-Term Examination 2024 - Solutions

## Question 1: Define baseband and broadband transmissions. Give an example of both transmission systems.

**Baseband Transmission:**
- Definition: Baseband transmission refers to the transmission of digital signals without modulation. The entire bandwidth of the medium is used to transmit a single signal.
- Example: Ethernet over twisted pair cables (10BASE-T, 100BASE-T) where digital signals are sent directly over the cable.

**Broadband Transmission:**
- Definition: Broadband transmission involves modulating digital signals to higher frequencies, allowing multiple signals to be transmitted simultaneously over different frequency bands on the same medium.
- Example: Cable television systems where multiple TV channels are transmitted simultaneously over different frequency bands on the same coaxial cable.

## Question 2: We have a baseband channel with 100kHz bandwidth. What is the data rate for this channel if we use each of the following line encoding techniques:

a) NRZ-L:
   Data rate = 2 × Bandwidth = 2 × 100 kHz = 200 kbps
   (According to Nyquist theorem for binary signals)

b) Manchester:
   Data rate = Bandwidth = 100 kHz = 100 kbps
   (Manchester encoding requires twice the bandwidth of NRZ for the same data rate, so with fixed bandwidth, the data rate is halved)

c) MLT-3:
   Data rate = 2 × Bandwidth = 2 × 100 kHz = 200 kbps
   (MLT-3 has spectral properties similar to NRZ for binary signals)

d) 2B1Q:
   Data rate = 2 × Bandwidth × log₂(L) = 2 × 100 kHz × log₂(4) = 2 × 100 kHz × 2 = 400 kbps
   (Where L=4 is the number of signal levels in 2B1Q encoding)

## Question 3: Distinguish between distortion and noise.

**Distortion:**
- Distortion is an unwanted change in the signal waveform that occurs during transmission through a communication channel.
- It is usually deterministic and caused by the physical characteristics of the channel itself.
- Examples include attenuation distortion (different frequency components attenuate differently), delay distortion (different frequency components travel at different speeds), and nonlinear distortion.
- Distortion can often be corrected or compensated for through equalization.

**Noise:**
- Noise refers to random, unpredictable electrical signals that are added to the transmitted signal.
- It is typically random and caused by external factors or internal components.
- Examples include thermal noise, impulse noise, crosstalk, and electromagnetic interference.
- Noise cannot be completely eliminated but can be reduced through techniques like filtering, shielding, and using error-correction codes.

## Question 4: Encode the bit pattern 0110110001110011010 using MLT-3, NRZ-L, RZ, Differential Manchester, Pseudo Ternary, and AMI schemes. Assume initial signal level was positive. Also sort the schemes ascendingly according to the DC offset they produce.

Let me encode the given bit stream with each scheme:

**MLT-3 Encoding:**
- Starting at +V level
- Transitions: +V → 0 → -V → 0 → +V (for each '1' bit)
- Signal levels: +V, +V, 0, -V, -V, 0, +V, +V, +V, 0, -V, 0, +V, 0, -V, -V, -V, 0, +V

**NRZ-L Encoding:**
- '0' = Low level (-V), '1' = High level (+V)
- Signal levels: -V, +V, +V, -V, +V, +V, -V, -V, -V, +V, +V, +V, -V, -V, +V, +V, -V, +V, -V

**RZ (Return to Zero) Encoding:**
- '0' = Low level for entire bit duration, '1' = High level for half bit duration, then zero
- For each bit period: -V/-V, +V/0, +V/0, -V/-V, +V/0, +V/0, -V/-V, -V/-V, -V/-V, +V/0, +V/0, +V/0, -V/-V, -V/-V, +V/0, +V/0, -V/-V, +V/0, -V/-V

**Differential Manchester:**
- Transition at middle of each bit period
- '0' = Additional transition at beginning of bit period, '1' = No transition at beginning
- Starting with transition from low to high at beginning for '0'
- Complex pattern with transitions at middle of each bit and additional transitions for '0' bits

**Pseudo Ternary:**
- '1' = Zero level, '0' = Alternating positive and negative pulses
- Starting with +V for first '0'
- Signal levels: +V, 0, 0, -V, 0, 0, +V, +V, +V, 0, 0, 0, +V, +V, 0, 0, +V, 0, +V

**AMI (Alternate Mark Inversion):**
- '0' = Zero level, '1' = Alternating positive and negative pulses
- Starting with +V for first '1'
- Signal levels: 0, +V, +V, 0, +V, +V, 0, 0, 0, +V, -V, +V, 0, 0, +V, -V, 0, +V, 0

**DC Offset Sorting (Ascending):**
1. Differential Manchester (zero DC component due to equal positive and negative transitions)
2. MLT-3 (very low DC component)
3. AMI (low DC component)
4. Pseudo Ternary (low DC component)
5. RZ (moderate DC component, depends on data pattern)
6. NRZ-L (highest DC component, highly dependent on data pattern)

## Question 5: A signal generator is producing a square wave with a period of 1ms. What happens (show illustrations in both time and frequency domains with possible explanations) when it is passed through:

### a) A lowpass filter with a cutoff frequency of 3KHz

**Time Domain Effect:**
- The square wave's sharp edges will be rounded.
- The waveform will resemble a sine wave as higher harmonics are removed.
- Some delay may be introduced.

**Frequency Domain Effect:**
- A square wave contains a fundamental frequency (1 kHz in this case, as T = 1ms) and odd harmonics (3 kHz, 5 kHz, 7 kHz, etc.).
- The lowpass filter with 3 kHz cutoff will pass the fundamental frequency (1 kHz) at full strength.
- The 3rd harmonic (3 kHz) will be attenuated by 3dB.
- All higher harmonics (5 kHz, 7 kHz, etc.) will be increasingly attenuated.
- This results in a frequency spectrum that is significantly reduced beyond 3 kHz.



### b) A highpass filter with a cutoff frequency of 3KHz

**Time Domain Effect:**
- The square wave will be transformed into sharp spikes at the transition edges.
- The flat portions of the square wave will be removed (as they are DC components).
- The resulting waveform resembles a differentiated square wave.

**Frequency Domain Effect:**
- The fundamental frequency (1 kHz) will be attenuated significantly.
- The 3rd harmonic (3 kHz) will be attenuated by 3dB.
- Higher harmonics (5 kHz, 7 kHz, etc.) will pass with less attenuation.
- This results in a frequency spectrum that is progressively stronger for higher frequencies.

 ![Midterm Exam Screenshot](https://github.com/Mdsadmansakib/Data-and-Telecommunication/blob/main/PYQ/Mid/SS_28.png?raw=true)

 
## Question 6: A signal is transmitted with a voltage level of +5V and -5V using a polar NRZ encoding scheme. If a noise level of -174dBm/Hz and attenuation of 1.5dB affect the signal and cause a voltage drop of 2V, what is the impact on decoding the signal at the receiver?

Original signal levels: +5V and -5V
After attenuation and voltage drop: +3.5V and -3.5V

The attenuated signal still maintains a clear distinction between positive and negative voltage levels. Since polar NRZ encoding uses positive voltage for '1' and negative voltage for '0', the receiver can still correctly distinguish between these two levels even after the voltage drop.

The noise level of -174dBm/Hz is extremely low (thermal noise floor), which means the signal-to-noise ratio is still very high. This noise level is unlikely to cause bit errors in the decoding process.

Therefore, the impact on decoding at the receiver is minimal, and reliable communication can still be maintained despite the attenuation and voltage drop.

## Question 7: Suppose the spectrum of a channel is between 100MHz and 103MHz and SNRdB = 20 dB. Find the theoretical maximum capacity of the channel considering the noise level. Also find the number of signal levels required to achieve the previously derived channel capacity.

**Channel Bandwidth** = 103 MHz - 100 MHz = 3 MHz = 3 × 10^6 Hz

**SNR** = 10^(SNRdB/10) = 10^(20/10) = 10^2 = 100

Using Shannon-Hartley Theorem:
C = B × log₂(1 + SNR)
C = 3 × 10^6 × log₂(1 + 100)
C = 3 × 10^6 × log₂(101)
C = 3 × 10^6 × 6.658 ≈ 19.97 × 10^6 bps ≈ 19.97 Mbps

To find the number of signal levels required using Nyquist formula:
C = 2B × log₂(L)

Where:
- C is the channel capacity (19.97 Mbps)
- B is the bandwidth (3 MHz)
- L is the number of signal levels

19.97 × 10^6 = 2 × 3 × 10^6 × log₂(L)
19.97 × 10^6 = 6 × 10^6 × log₂(L)
log₂(L) = 19.97 × 10^6 / (6 × 10^6) ≈ 3.33
L = 2^3.33 ≈ 10.06 ≈ 10 levels

Therefore, approximately 10 signal levels would be required to achieve the maximum channel capacity.
