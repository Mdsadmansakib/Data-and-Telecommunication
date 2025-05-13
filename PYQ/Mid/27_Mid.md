# CSE2203: Data Communications Mid-Term Examination 2022 - Solutions

## Question 1: We need to upgrade a channel to a higher bandwidth. Answer the following questions:

### i) How is the rate improved if we double the bandwidth?

According to Shannon's channel capacity formula:
C = B × log₂(1 + SNR)

If we double the bandwidth (B → 2B), the capacity becomes:
C' = 2B × log₂(1 + SNR)
C' = 2C

Therefore, doubling the bandwidth results in doubling the channel capacity (rate).

### ii) How is the rate improved if we double the SNR?

If we double the SNR (SNR → 2×SNR), the capacity becomes:
C' = B × log₂(1 + 2×SNR)

This does not double the capacity but increases it by:
C' = B × log₂(1 + 2×SNR) < 2 × B × log₂(1 + SNR) = 2C

The improvement is less than doubling because the logarithmic relationship means diminishing returns for increases in SNR.

## Question 2: Define baseband and broadband transmissions. Give examples of both transmission systems.

**Baseband Transmission:**
- Definition: Baseband transmission refers to the transmission of digital signals without modulation. The entire bandwidth of the medium is used to transmit a single signal.
- Example: Ethernet over twisted pair cables (10BASE-T, 100BASE-T) where digital signals are sent directly over the cable.

**Broadband Transmission:**
- Definition: Broadband transmission involves modulating digital signals to higher frequencies, allowing multiple signals to be transmitted simultaneously over different frequency bands on the same medium.
- Example: Cable television systems where multiple TV channels are transmitted simultaneously over different frequency bands on the same coaxial cable.

## Question 3: A composite signal is given by the following function f(t) = (1 + 0.1cos100πt)sin100t. Find the amplitude, phase, and frequency of that signal and represent it in frequency domain. [2sinx cosx = sin(x+y)+sin(x-y)]

The given signal f(t) = (1 + 0.1cos100πt)sin100t can be rewritten as:
f(t) = sin100t + 0.1cos100πt·sin100t

Using the identity 2sinx·cosy = sin(x+y) + sin(x-y):
0.1cos100πt·sin100t = 0.1/2[sin(100t+100πt) + sin(100t-100πt)]
= 0.05sin(100t+100πt) + 0.05sin(100t-100πt)

Since 100t = 100πt·(1/π), the terms become:
= 0.05sin(100πt·(1/π+1)) + 0.05sin(100πt·(1/π-1))
= 0.05sin(100πt·(1+π)/π) + 0.05sin(100πt·(1-π)/π)

Therefore, f(t) = sin100t + 0.05sin(100πt·(1+π)/π) + 0.05sin(100πt·(1-π)/π)

In the frequency domain:
- The main carrier: sin100t has frequency ω₁ = 100 rad/s (or f₁ = 50/π Hz) and amplitude 1
- Upper sideband: 0.05sin(100πt·(1+π)/π) has frequency ω₂ = 100π·(1+π)/π rad/s and amplitude 0.05
- Lower sideband: 0.05sin(100πt·(1-π)/π) has frequency ω₃ = 100π·(1-π)/π rad/s and amplitude 0.05

This represents amplitude modulation with a carrier frequency of 50/π Hz, modulated by a signal of frequency 50 Hz, with a modulation index of 0.1.

## Question 4: Distinguish between distortion and noise.

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

## Question 5: Encode the bit pattern 10101100111001110011 using Differential Manchester, Pseudo Ternary, and AMI schemes.

**Differential Manchester:**
- In Differential Manchester, there is always a transition in the middle of each bit period.
- A '0' bit is represented by having a transition at the beginning of the bit period.
- A '1' bit is represented by having no transition at the beginning of the bit period.
- Assuming we start with a transition from low to high at the beginning:
  - Bit pattern: 1 0 1 0 1 1 0 0 1 1 1 0 0 1 1 1 0 0 1 1
  - Result: ─┐_┌─┐_┌┐_┌┐_┐_┐_┌┐_┌─┐_┐_┐_┐_┌┐_┌─┐_┐_┐_
    (where high level is shown as "_" at top, low level as "_" at bottom)

**Pseudo Ternary:**
- In Pseudo Ternary, '1' is represented by a zero voltage level.
- '0' is represented by alternating positive and negative voltage levels.
- Starting with positive voltage for the first '0':
  - Bit pattern: 1 0 1 0 1 1 0 0 1 1 1 0 0 1 1 1 0 0 1 1
  - Result: 0 + 0 - 0 0 + - 0 0 0 + - 0 0 0 + - 0 0
    (where '+' represents positive voltage, '-' represents negative voltage, and '0' represents zero voltage)

**AMI (Alternate Mark Inversion):**
- In AMI, '0' is represented by a zero voltage level.
- '1' is represented by alternating positive and negative voltage levels.
- Starting with positive voltage for the first '1':
  - Bit pattern: 1 0 1 0 1 1 0 0 1 1 1 0 0 1 1 1 0 0 1 1
  - Result: + 0 - 0 + - 0 0 + - + 0 0 - + - 0 0 + -
    (where '+' represents positive voltage, '-' represents negative voltage, and '0' represents zero voltage)

## Question 6: In modern packet-switched networks, including the Internet, the source host segments long, application-layer messages into smaller packets and sends the packets into the network. The receiver then reassembles the packets back into the original message. Consider a message that is 8 x 10^6 bits long that is to be sent from source to destination in the figure below. Suppose each link in the figure is 2 Mbps. Ignore propagation, queuing, and processing delays.

Now suppose that the message is segmented into 800 packets, with each packet being 10,000 bits long. Keeping in mind that each switch uses store-and-forward packet switching, how long does it take to move the first packet from source host to the first switch? When the first packet is being sent from the first switch to the second switch, the second packet is being sent from the source host to the first switch. At what time will the second packet be fully received at the first switch?

**Solution:**

Given:
- Message size = 8 × 10^6 bits
- Number of packets = 800
- Packet size = 10,000 bits
- Link rate = 2 Mbps = 2 × 10^6 bits/second

**Time to move the first packet from source host to the first switch:**
- Transmission time = Packet size / Link rate
- Transmission time = 10,000 bits / (2 × 10^6 bits/second)
- Transmission time = 5 × 10^-3 seconds = 5 milliseconds

So it takes 5 milliseconds for the first packet to move from the source host to the first switch.

**Time when the second packet will be fully received at the first switch:**
- The second packet begins transmission from the source host just after the first packet's transmission is complete, i.e., at 5 milliseconds.
- The second packet's transmission also takes 5 milliseconds.
- Therefore, the second packet will be fully received at the first switch at 5 + 5 = 10 milliseconds.

## Question 7: Suppose that a digitized TV picture is to be transmitted from source that uses a matrix of 480x500 picture elements (pixels), where each pixel can take on one of 32 intensity values. Assume that 30 pictures are sent per second. Assume that the TV picture is to be transmitted over channel with a 4.5 Mhz bandwidth and a 35 dB signal-to-noise ratio. Find the capacity of the channel (bps).

Given:
- Resolution = 480 × 500 = 240,000 pixels per frame
- Intensity values = 32 = 2^5, so 5 bits per pixel
- Frame rate = 30 frames per second
- Bandwidth = 4.5 MHz = 4.5 × 10^6 Hz
- SNR = 35 dB

**Required data rate for the TV transmission:**
- Data rate = Number of pixels × Bits per pixel × Frames per second
- Data rate = 240,000 × 5 × 30 = 36,000,000 bps = 36 Mbps

**Channel capacity using Shannon-Hartley theorem:**
- C = B × log₂(1 + SNR)
- SNR_linear = 10^(SNR_dB/10) = 10^(35/10) = 10^3.5 ≈ 3162.28
- C = 4.5 × 10^6 × log₂(1 + 3162.28)
- C = 4.5 × 10^6 × log₂(3163.28)
- C = 4.5 × 10^6 × 11.63 ≈ 52.33 × 10^6 bps ≈ 52.33 Mbps

Therefore, the channel capacity is approximately 52.33 Mbps, which is sufficient to transmit the digitized TV signal requiring 36 Mbps.

## Question 8: Is it possible to change the phase of a signal without changing the instantaneous frequency and vice versa? Justify your answer.

**Yes, it is possible to change the phase of a signal without changing the instantaneous frequency, and vice versa.**

Justification:

1. **Changing phase without changing frequency:**
   - Consider a sinusoidal signal x(t) = A·sin(ωt)
   - Adding a phase shift: y(t) = A·sin(ωt + φ)
   - The instantaneous frequency is still ω for both signals, but the phase differs by φ
   - This is commonly used in phase modulation, where information is encoded in phase shifts while keeping the frequency constant

2. **Changing frequency without changing phase:**
   - Consider a sinusoidal signal x(t) = A·sin(ω₁t)
   - At t=0, the phase is 0 (or sine starts at 0)
   - If we change to y(t) = A·sin(ω₂t) at precisely the moment when sin(ω₁t) = 0 and the slope is positive
   - The phase at the transition point remains the same (0), but the frequency changes
   - This is used in frequency modulation, where information is encoded in frequency changes

In practical communications, phase and frequency modulation are distinct techniques because of this ability to change one without necessarily affecting the other.

## Question 9: Differentiate between the operations of physical layer and data link layer in the context of OSI model.

**Physical Layer:**
- Concerned with the transmission and reception of raw bit stream over a physical medium
- Defines physical characteristics of interfaces and media (voltage levels, timing, etc.)
- Handles bit-by-bit delivery
- Provides mechanical, electrical, functional, and procedural means for activating and maintaining connections
- Examples of functions: bit synchronization, bit rate control, physical topologies, transmission mode

**Data Link Layer:**
- Responsible for reliable node-to-node (hop-to-hop) delivery of data frames
- Handles error detection and correction to ensure reliable transmission
- Provides framing mechanisms to encapsulate raw bits from physical layer into frames
- Manages flow control between adjacent nodes
- Controls access to shared media through Media Access Control (MAC) protocols
- Examples of functions: framing, addressing, error control, flow control, media access control

**Key Differences:**
1. **Unit of Data**: Physical layer deals with bits, while data link layer deals with frames
2. **Addressing**: Physical layer has no addressing; data link layer uses physical (MAC) addresses
3. **Error Handling**: Physical layer provides only transmission, while data link layer includes error detection and correction
4. **Media Access**: Physical layer defines physical media characteristics, while data link layer controls access to shared media
5. **Reliability**: Physical layer provides unreliable delivery, while data link layer aims for reliable delivery

## Question 10: A signal generator is producing a square wave with a period of 1ms. What happens (show illustrations with possible reasons) when it is passed through:

### i) A lowpass filter with a cutoff frequency of 3KHz

**Effects in Time Domain:**
- The square wave's sharp edges will be rounded.
- The waveform will resemble a sine wave as higher harmonics are removed.
- Some delay may be introduced.

**Explanation:**
A square wave with period 1ms has a fundamental frequency of 1kHz. It can be represented as a Fourier series of sine waves:
Square wave = (4/π) × [sin(2πft) + (1/3)sin(6πft) + (1/5)sin(10πft) + ...]

Where f = 1kHz is the fundamental frequency.

The lowpass filter with cutoff frequency 3kHz will:
- Pass the fundamental frequency (1kHz) without attenuation
- Pass the 3rd harmonic (3kHz) with -3dB attenuation
- Significantly attenuate the 5th harmonic (5kHz) and higher harmonics

The resulting waveform will be much smoother than the original square wave, resembling a sine wave with some distortion.

### ii) A highpass filter with a cutoff frequency of 3KHz

**Effects in Time Domain:**
- The square wave will be transformed into sharp spikes at the transition edges.
- The flat portions of the square wave will be removed.
- The resulting waveform resembles a differentiated square wave.

**Explanation:**
The highpass filter with cutoff frequency 3kHz will:
- Significantly attenuate the fundamental frequency (1kHz)
- Attenuate the 3rd harmonic (3kHz) by -3dB
- Pass higher harmonics (5kHz and above) with minimal attenuation

This preserves only the high-frequency components that are responsible for the sharp transitions in the square wave. Since the DC component and low-frequency components are removed, the flat portions of the square wave disappear, leaving only the spikes at the transitions.

The resulting waveform will consist of positive and negative spikes occurring at the rising and falling edges of the original square wave, similar to what would be produced by differentiating the square wave.
