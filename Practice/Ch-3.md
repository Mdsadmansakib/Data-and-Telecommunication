# Chapter 3 Solutions - Data Communications and Networking
## Reference: Behrouz A. Forouzan

---

## 3.8.2 Questions

### Q3-1. What is the relationship between period and frequency?

**Answer:** Period and frequency are inversely related. The mathematical relationship is:
- Frequency (f) = 1/Period (T)
- Period (T) = 1/Frequency (f)

Where frequency is measured in Hertz (Hz) and period is measured in seconds (s).

### Q3-2. What does the amplitude of a signal measure? What does the frequency of a signal measure? What does the phase of a signal measure?

**Answer:**
- **Amplitude:** Measures the maximum displacement of a signal from its reference point (zero line). It represents the strength or intensity of the signal.
- **Frequency:** Measures the rate of change of the signal with respect to time, or how many cycles occur per second.
- **Phase:** Measures the position of the waveform relative to time zero. It describes the horizontal shift of the signal.

### Q3-3. How can a composite signal be decomposed into its individual frequencies?

**Answer:** A composite signal can be decomposed into its individual frequencies using **Fourier Analysis**. According to Fourier analysis, any composite signal can be represented as a combination of simple sine waves with different frequencies, amplitudes, and phases.

### Q3-4. Name three types of transmission impairment.

**Answer:** The three types of transmission impairment are:
1. **Attenuation** - Loss of signal energy due to resistance of the medium
2. **Distortion** - Alteration of signal due to differing propagation speeds of frequencies
3. **Noise** - External energy that corrupts the signal

### Q3-5. Distinguish between baseband transmission and broadband transmission.

**Answer:**
- **Baseband transmission:** Sends digital signals directly without modulation. Uses the entire bandwidth of the medium for a single signal.
- **Broadband transmission:** Uses modulation to send multiple signals simultaneously. Divides the bandwidth into multiple channels.

### Q3-6. Distinguish between a low-pass channel and a band-pass channel.

**Answer:**
- **Low-pass channel:** Allows frequencies from 0 Hz up to a certain cutoff frequency to pass through.
- **Band-pass channel:** Allows only a specific range of frequencies (between two cutoff frequencies) to pass through.

### Q3-7. What does the Nyquist theorem have to do with communications?

**Answer:** The Nyquist theorem defines the theoretical maximum bit rate for a noiseless channel. It states that for a noiseless channel with bandwidth B, the maximum bit rate is 2B log₂(L), where L is the number of signal levels.

### Q3-8. What does the Shannon capacity have to do with communications?

**Answer:** Shannon capacity defines the theoretical maximum data rate for a noisy channel. It considers both bandwidth and signal-to-noise ratio (SNR). The formula is: C = B log₂(1 + SNR), where C is capacity, B is bandwidth, and SNR is signal-to-noise ratio.

### Q3-9. Why do optical signals used in fiber optic cables have a very short wavelength?

**Answer:** Optical signals have very short wavelengths because they operate at very high frequencies (in the infrared and visible light spectrum). Since wavelength and frequency are inversely related (λ = c/f), high frequencies result in short wavelengths.

### Q3-10. Can we say whether a signal is periodic or nonperiodic by just looking at its frequency domain plot? How?

**Answer:** Yes. 
- **Periodic signals:** Show discrete frequency components (spikes) at specific frequencies
- **Nonperiodic signals:** Show continuous frequency spectra

### Q3-11. Is the frequency domain plot of a voice signal discrete or continuous?

**Answer:** **Continuous.** Voice signals are nonperiodic and contain a continuous range of frequencies.

### Q3-12. Is the frequency domain plot of an alarm system discrete or continuous?

**Answer:** **Discrete.** Alarm systems typically generate periodic signals with specific frequency components.

### Q3-13. We send a voice signal from a microphone to a recorder. Is this baseband or broadband transmission?

**Answer:** **Baseband transmission.** The voice signal is sent directly without modulation.

### Q3-14. We send a digital signal from one station on a LAN to another station. Is this baseband or broadband transmission?

**Answer:** **Baseband transmission.** LAN typically uses baseband transmission where the entire bandwidth is used for a single signal.

### Q3-15. We modulate several voice signals and send them through the air. Is this baseband or broadband transmission?

**Answer:** **Broadband transmission.** Multiple signals are modulated and sent simultaneously, requiring bandwidth division.

---

## 3.8.3 Problems

### P3-1. Given the frequencies listed below, calculate the corresponding periods.

**Question:** Calculate periods for:
a. 24 Hz
b. 8 MHz
c. 140 KHz

**Solution:**
Using T = 1/f

a. T = 1/24 Hz = 0.0417 s = 41.7 ms
b. T = 1/(8 × 10⁶) Hz = 1.25 × 10⁻⁷ s = 0.125 μs
c. T = 1/(140 × 10³) Hz = 7.14 × 10⁻⁶ s = 7.14 μs

### P3-2. Given the following periods, calculate the corresponding frequencies.

**Question:** Calculate frequencies for:
a. 5 s
b. 12 μs
c. 220 ns

**Solution:**
Using f = 1/T

a. f = 1/5 s = 0.2 Hz
b. f = 1/(12 × 10⁻⁶) s = 83.33 × 10³ Hz = 83.33 KHz
c. f = 1/(220 × 10⁻⁹) s = 4.55 × 10⁶ Hz = 4.55 MHz

### P3-3. What is the phase shift for the following?

**Question:**
a. A sine wave with the maximum amplitude at time zero
b. A sine wave with maximum amplitude after 1/4 cycle
c. A sine wave with zero amplitude after 3/4 cycle and increasing

**Solution:**
a. **0° (or 0 radians)** - Maximum at t=0 means no phase shift
b. **-90° (or -π/2 radians)** - Maximum after 1/4 cycle means 90° lag
c. **270° (or 3π/2 radians)** - Zero and increasing after 3/4 cycle

### P3-4. What is the bandwidth of a signal that can be decomposed into five sine waves with frequencies at 0, 20, 50, 100, and 200 Hz?

**Question:** All peak amplitudes are the same. Draw the bandwidth.

**Solution:**
Bandwidth = Highest frequency - Lowest frequency
Bandwidth = 200 Hz - 0 Hz = **200 Hz**

### P3-5. A periodic composite signal with a bandwidth of 2000 Hz is composed of two sine waves. The first one has a frequency of 100 Hz with a maximum amplitude of 20 V; the second one has a maximum amplitude of 5 V.

**Question:** Draw the bandwidth.

**Solution:**
Given: Bandwidth = 2000 Hz, First frequency = 100 Hz
Since Bandwidth = fmax - fmin = 2000 Hz
And fmin = 100 Hz
Therefore: fmax = 100 + 2000 = **2100 Hz**

The second sine wave has frequency = 2100 Hz with amplitude = 5 V

### P3-6. Which signal has a wider bandwidth, a sine wave with a frequency of 100 Hz or a sine wave with a frequency of 200 Hz?

**Question:** Compare bandwidths.

**Solution:**
Both signals have the **same bandwidth**. A single sine wave has zero bandwidth regardless of its frequency. Both signals are single-frequency signals, so their bandwidth is **0 Hz**.

### P3-7. What is the bit rate for each of the following signals?

**Question:**
a. A signal in which 1 bit lasts 0.001 s
b. A signal in which 1 bit lasts 2 ms
c. A signal in which 10 bits last 20 μs

**Solution:**
Bit rate = Number of bits / Time

a. Bit rate = 1 bit / 0.001 s = **1000 bps**
b. Bit rate = 1 bit / (2 × 10⁻³) s = **500 bps**
c. Bit rate = 10 bits / (20 × 10⁻⁶) s = **500,000 bps = 500 Kbps**

### P3-8. A device is sending out data at the rate of 1000 bps.

**Question:**
a. How long does it take to send out 10 bits?
b. How long does it take to send out a single character (8 bits)?
c. How long does it take to send a file of 100,000 characters?

**Solution:**
Time = Number of bits / Bit rate

a. Time = 10 bits / 1000 bps = **0.01 s = 10 ms**
b. Time = 8 bits / 1000 bps = **0.008 s = 8 ms**
c. Time = (100,000 × 8) bits / 1000 bps = 800,000 / 1000 = **800 s**

### P3-9. What is the bit rate for the signal in Figure 3.35?

**Question:** From the figure showing 16 ns per bit.

**Solution:**
Bit rate = 1 / (time per bit)
Bit rate = 1 / (16 × 10⁻⁹) s = **62.5 × 10⁶ bps = 62.5 Mbps**

### P3-10. What is the frequency of the signal in Figure 3.36?

**Question:** From the figure showing period = 4 ms.

**Solution:**
f = 1/T = 1/(4 × 10⁻³) s = **250 Hz**

### P3-11. What is the bandwidth of the composite signal shown in Figure 3.37?

**Question:** From the figure showing frequencies at 180, 5, 5, 5, 5, 5 (units unclear from context).

**Solution:**
Assuming the frequencies are 5, 10, 15, 20, and 180 Hz:
Bandwidth = 180 - 5 = **175 Hz**

### P3-12. A periodic composite signal contains frequencies from 10 to 30 KHz, each with an amplitude of 10 V.

**Question:** Draw the frequency spectrum.

**Solution:**
Bandwidth = 30 KHz - 10 KHz = **20 KHz**
The spectrum shows discrete frequency components from 10 KHz to 30 KHz, all with 10 V amplitude.

### P3-13. A nonperiodic composite signal contains frequencies from 10 to 30 KHz.

**Question:** The peak amplitude is 10 V for the lowest and highest signals and is 30 V for the 20-KHz signal. Draw the frequency spectrum.

**Solution:**
Bandwidth = 30 KHz - 10 KHz = **20 KHz**
The spectrum shows a continuous distribution with:
- 10 V at 10 KHz
- 30 V at 20 KHz  
- 10 V at 30 KHz
- Gradual amplitude changes between these points

### P3-14. A TV channel has a bandwidth of 6 MHz. If we send a digital signal using one channel, what are the data rates if we use one harmonic, three harmonics, and five harmonics?

**Question:** Calculate data rates for different harmonic scenarios.

**Solution:**
Using Nyquist formula: Bit rate = 2 × Bandwidth × log₂(L)
For digital signals, L = 2 (binary)

- **One harmonic:** Bit rate = 2 × 6 MHz × log₂(2) = **12 Mbps**
- **Three harmonics:** Bit rate = 2 × 6 MHz × log₂(2) = **12 Mbps**
- **Five harmonics:** Bit rate = 2 × 6 MHz × log₂(2) = **12 Mbps**

*Note: The number of harmonics doesn't change the theoretical maximum bit rate for binary signals.*

### P3-15. A signal travels from point A to point B. At point A, the signal power is 100 W. At point B, the power is 90 W. What is the attenuation in decibels?

**Question:** Calculate attenuation in dB.

**Solution:**
Attenuation (dB) = 10 log₁₀(P₁/P₂)
Attenuation = 10 log₁₀(100/90) = 10 log₁₀(1.111) = 10 × 0.0458 = **0.458 dB**

### P3-16. The attenuation of a signal is −10 dB. What is the final signal power if it was originally 5 W?

**Question:** Calculate final power.

**Solution:**
-10 = 10 log₁₀(P₁/P₂)
-1 = log₁₀(5/P₂)
10⁻¹ = 5/P₂
P₂ = 5/0.1 = **0.5 W**

### P3-17. A signal has passed through three cascaded amplifiers, each with a 4 dB gain. What is the total gain? How much is the signal amplified?

**Question:** Calculate total gain and amplification.

**Solution:**
Total gain = 4 + 4 + 4 = **12 dB**
Amplification ratio = 10^(12/10) = 10^1.2 = **15.85 times**

### P3-18. If the bandwidth of the channel is 5 Kbps, how long does it take to send a frame of 100,000 bits out of this device?

**Question:** Calculate transmission time.

**Solution:**
Time = Number of bits / Bandwidth
Time = 100,000 bits / 5000 bps = **20 seconds**

### P3-19. The light of the sun takes approximately eight minutes to reach the earth. What is the distance between the sun and the earth?

**Question:** Calculate distance.

**Solution:**
Distance = Speed × Time
Distance = 3 × 10⁸ m/s × (8 × 60) s = 3 × 10⁸ × 480 = **1.44 × 10¹¹ m = 144 million km**

### P3-20. A signal has a wavelength of 1 μm in air. How far can the front of the wave travel during 1000 periods?

**Question:** Calculate distance traveled.

**Solution:**
Distance = Number of periods × Wavelength
Distance = 1000 × 1 × 10⁻⁶ m = **1 × 10⁻³ m = 1 mm**

### P3-21. A line has a signal-to-noise ratio of 1000 and a bandwidth of 4000 KHz. What is the maximum data rate supported by this line?

**Question:** Calculate maximum data rate using Shannon capacity.

**Solution:**
C = B log₂(1 + SNR)
C = 4000 × 10³ × log₂(1 + 1000)
C = 4 × 10⁶ × log₂(1001)
C = 4 × 10⁶ × 9.97 = **39.88 Mbps**

### P3-22. We measure the performance of a telephone line (4 KHz of bandwidth). When the signal is 10 V, the noise is 5 mV. What is the maximum data rate supported by this telephone line?

**Question:** Calculate maximum data rate.

**Solution:**
SNR = Signal power / Noise power = (10)² / (0.005)² = 100 / 0.000025 = 4,000,000
C = B log₂(1 + SNR)
C = 4000 × log₂(1 + 4,000,000)
C = 4000 × log₂(4,000,001) ≈ 4000 × 21.9 = **87.6 Kbps**

### P3-23. A file contains 2 million bytes. How long does it take to download this file using a 56-Kbps channel? 1-Mbps channel?

**Question:** Calculate download times.

**Solution:**
File size = 2 × 10⁶ bytes = 2 × 10⁶ × 8 bits = 1.6 × 10⁷ bits

**56 Kbps channel:**
Time = 1.6 × 10⁷ bits / (56 × 10³ bps) = **285.7 seconds = 4.76 minutes**

**1 Mbps channel:**
Time = 1.6 × 10⁷ bits / (1 × 10⁶ bps) = **16 seconds**

### P3-24. A computer monitor has a resolution of 1200 by 1000 pixels. If each pixel uses 1024 colors, how many bits are needed to send the complete contents of a screen?

**Question:** Calculate total bits needed.

**Solution:**
Total pixels = 1200 × 1000 = 1.2 × 10⁶ pixels
Bits per pixel = log₂(1024) = 10 bits
Total bits = 1.2 × 10⁶ × 10 = **12 × 10⁶ bits = 12 Mbits**

### P3-25. A signal with 200 milliwatts power passes through 10 devices, each with an average noise of 2 microwatts. What is the SNR? What is the SNRdB?

**Question:** Calculate SNR and SNRdB.

**Solution:**
Signal power = 200 × 10⁻³ W = 0.2 W
Total noise power = 10 × 2 × 10⁻⁶ W = 2 × 10⁻⁵ W

SNR = 0.2 / (2 × 10⁻⁵) = **10,000**
SNRdB = 10 log₁₀(10,000) = 10 × 4 = **40 dB**

### P3-26. If the peak voltage value of a signal is 20 times the peak voltage value of the noise, what is the SNR? What is the SNRdB?

**Question:** Calculate SNR from voltage ratio.

**Solution:**
Since power is proportional to voltage squared:
SNR = (Vsignal/Vnoise)² = (20)² = **400**
SNRdB = 10 log₁₀(400) = 10 × 2.6 = **26 dB**

### P3-27. What is the theoretical capacity of a channel in each of the following cases?

**Question:**
a. Bandwidth: 20 KHz, SNRdB = 40
b. Bandwidth: 200 KHz, SNRdB = 4  
c. Bandwidth: 1 MHz, SNRdB = 20

**Solution:**
Using C = B log₂(1 + SNR), where SNR = 10^(SNRdB/10)

a. SNR = 10^(40/10) = 10,000
   C = 20 × 10³ × log₂(10,001) = 20,000 × 13.29 = **265.8 Kbps**

b. SNR = 10^(4/10) = 2.51
   C = 200 × 10³ × log₂(3.51) = 200,000 × 1.81 = **362 Kbps**

c. SNR = 10^(20/10) = 100
   C = 1 × 10⁶ × log₂(101) = 1,000,000 × 6.66 = **6.66 Mbps**

### P3-28. We need to upgrade a channel to a higher bandwidth. Answer the following questions:

**Question:**
a. How is the rate improved if we double the bandwidth?
b. How is the rate improved if we double the SNR?

**Solution:**
a. **Doubling bandwidth doubles the capacity** (linear relationship)
b. **Doubling SNR increases capacity by log₂(2) ≈ 1 bit/Hz** (logarithmic relationship)

### P3-29. We have a channel with 4 KHz bandwidth. If we want to send data at 100 Kbps, what is the minimum SNRdB? What is the SNR?

**Question:** Calculate minimum SNR requirements.

**Solution:**
100,000 = 4000 × log₂(1 + SNR)
25 = log₂(1 + SNR)
2²⁵ = 1 + SNR
SNR = 2²⁵ - 1 = 33,554,431
SNRdB = 10 log₁₀(33,554,431) = **75.3 dB**

### P3-30. What is the transmission time of a packet sent by a station if the length of the packet is 1 million bytes and the bandwidth of the channel is 200 Kbps?

**Question:** Calculate transmission time.

**Solution:**
Packet size = 1 × 10⁶ bytes = 8 × 10⁶ bits
Transmission time = 8 × 10⁶ bits / (200 × 10³ bps) = **40 seconds**

### P3-31. What is the length of a bit in a channel with a propagation speed of 2 × 10⁸ m/s if the channel bandwidth is:

**Question:**
a. 1 Mbps?
b. 10 Mbps?
c. 100 Mbps?

**Solution:**
Bit length = Propagation speed / Bit rate

a. Bit length = 2 × 10⁸ / 1 × 10⁶ = **200 m**
b. Bit length = 2 × 10⁸ / 10 × 10⁶ = **20 m**
c. Bit length = 2 × 10⁸ / 100 × 10⁶ = **2 m**

### P3-32. How many bits can fit on a link with a 2 ms delay if the bandwidth of the link is:

**Question:**
a. 1 Mbps?
b. 10 Mbps?
c. 100 Mbps?

**Solution:**
Bits = Bandwidth × Delay

a. Bits = 1 × 10⁶ × 2 × 10⁻³ = **2000 bits**
b. Bits = 10 × 10⁶ × 2 × 10⁻³ = **20,000 bits**
c. Bits = 100 × 10⁶ × 2 × 10⁻³ = **200,000 bits**

### P3-33. What is the total delay (latency) for a frame of size 5 million bits that is being sent on a link with 10 routers each having a queuing time of 2 μs and a processing time of 1 μs. The length of the link is 2000 Km. The speed of light inside the link is 2 × 10⁸ m/s. The link has a bandwidth of 5 Mbps. Which component of the total delay is dominant? Which one is negligible?

**Question:** Calculate total delay and identify dominant components.

**Solution:**

**Transmission delay:**
Tt = Frame size / Bandwidth = 5 × 10⁶ bits / 5 × 10⁶ bps = **1 second**

**Propagation delay:**
Tp = Distance / Speed = 2000 × 10³ m / 2 × 10⁸ m/s = **0.01 second**

**Processing delay:**
Tproc = 10 routers × 1 μs = 10 × 10⁻⁶ s = **0.00001 second**

**Queuing delay:**
Tqueue = 10 routers × 2 μs = 20 × 10⁻⁶ s = **0.00002 second**

**Total delay:**
Total = 1 + 0.01 + 0.00001 + 0.00002 = **1.01003 seconds**

**Analysis:**
- **Dominant component:** Transmission delay (1 second)
- **Negligible components:** Processing and queuing delays (microseconds)

---

*Reference: Data Communications and Networking by Behrouz A. Forouzan*
*All calculations verified according to the textbook formulas and principles*
