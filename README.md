# Laboratory-Midsommar
### Laboratory #2 (Experiment 9-14) :page_facing_up: 
### Introduction:
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This series of experiments traces the evolution of communication technology from advanced analog modulation to modern digital transmission. The curriculum begins with Frequency Modulation (FM), demonstrating its superiority in noisy environments over amplitude-based systems. It then transitions into the digital domain, exploring the Sampling Theorem and Pulse Code Modulation (PCM). By building and testing encoders, decoders, and channel filters, these labs illustrate how physical limitations—such as bandwidth and synchronization—impact the ability to transmit and recover high-fidelity information in a digital world.
</p>

---

### Objectives:
* To practically investigate and demonstrate the principles of modern telecommunications through hands-on experimentation.
* To compare the noise resistance of frequency-modulated (FM) signals against amplitude-modulated (AM) systems.
* To analyze the end-to-end process of digitizing analog information through sampling, quantization, and Pulse Code Modulation (PCM).
* To examine the critical role of synchronization and bandwidth limitations in the successful transmission and recovery of digital data.

---

### Explanations of Experiments:
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;In the analog phase (Exp 9-10), we see that information is best protected from noise by hiding it in the timing (frequency) of a wave rather than its strength (amplitude). However, for modern computing, signals must be converted into "bits." This requires Sampling (Exp 11), where we take "snapshots" of a wave. To turn these snapshots into data, we use PCM Encoding (Exp 12), which rounds the snapshots to the nearest number (quantization) and sends them as binary code.
</p>
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The most critical challenge revealed in this series is the Physical Reality of the Channel. No matter how perfect the digital code is, the wires and air it travels through (Exp 14) will always blur and distort the pulses. Therefore, communication is not just about sending data, but about managing Synchronization (Exp 13) and using hardware like filters and comparators to "clean up" the signal at the finish line.
</p>

---

<details>
<summary>EXPERIMENT 9: Frequency Modulation</summary> 

**INTRODUCTION**
* Explores FM as a robust alternative to amplitude modulation, demonstrating how varying a carrier’s frequency rather than its amplitude provides superior resistance to electrical noise.

**EXPLANATION**
* By using a Voltage Controlled Oscillator (VCO), an analog message is used to shift the carrier frequency. The amount of "swing" depends on the message's amplitude, while the speed of that swing depends on the message's frequency.

**WAVEFORM RESULT EXAMPLE**
<img width="1536" height="2048" alt="image" src="https://github.com/user-attachments/assets/5036cfd5-fe86-441b-a349-67f4f0a01356" />

[View Experiment 9 Details] https://github.com/EmmanAbad/Laboratory-Midsommar/blob/main/EXPERIMENT%209%20-%20Frequency%20Modulation.md

</details>

---
<details>
<summary>EXPERIMENT 10: FM Demodulation</summary>

**INTRODUCTION**
* Focuses on the "Zero-Crossing Detector" method to recover original messages from FM signals by converting frequency variations into measurable voltage changes.

**EXPLANATION**
* The FM signal is "squared up" using a comparator to trigger a pulse generator. Because the pulses have a fixed width, changing the frequency changes the duty cycle. A low-pass filter then averages these pulses to reconstruct the original wave.

**WAVEFORM RESULT EXAMPLE**
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/8934f2f8-df79-4b29-8b18-b1e31d934578" />

[View Experiment 10 Details] https://github.com/EmmanAbad/Laboratory-Midsommar/blob/main/EXPERIMENT%2010%20-%20FM%20Demodulation.md


</details>

---
<details>
<summary>EXPERIMENT 11: Sampling and Reconstruction</summary> 

**INTRODUCTION**
* Investigates the conversion of continuous analog signals into discrete digital formats through regular measurements of voltage.

**EXPLANATION**
* This lab proves the Nyquist Theorem: sampling a signal at least twice as fast as its highest frequency allows for perfect reconstruction. It demonstrates how "Sample and Hold" signals are smoothed back into analog form using filters.

**WAVEFORM RESULT EXAMPLE**
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/b1f7f952-b649-4da2-abf4-1bf4244fef30" />

[View Experiment 11 Details] https://github.com/EmmanAbad/Laboratory-Midsommar/blob/main/EXPERIMENT%2011%20-%20Sampling%20and%20Reconstruction.md

</details>

---

<details>
<summary>EXPERIMENT 12: PCM Encoding</summary>

**INTRODUCTION**
* Analyzes the fundamentals of digitizing analog voltages by sampling, quantizing, and converting them into an 8-bit serial binary stream.

**EXPLANATION**
* Each analog sample is compared to 256 quantization levels. The encoder assigns the closest binary number to that voltage. This lab highlights "quantization error"—the loss of detail that occurs when a signal is rounded to the nearest digital level.

**WAVEFORM RESULT EXAMPLE**
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/37576e84-703d-44fb-aaea-a33d1d5e8f2b" />

[View Experiment 12 Details] https://github.com/EmmanAbad/Laboratory-Midsommar/blob/main/EXPERIMENT%2012%20-%20PCM%20Encoding.md

</details>

---
<details>
<summary> EXPERIMENT 13: PCM Decoding</summary>

**INTRODUCTION**
* Examines the recovery of analog messages from serial binary data, emphasizing the necessity of precise timing between the transmitter and receiver.

**EXPLANATION**
* The decoder reads the 8-bit strings and converts them back into proportional voltages. Without a shared "Clock" and "Frame Sync" signal, the decoder cannot identify where a binary number begins or ends, leading to total signal loss.

**WAVEFORM RESULT EXAMPLE**
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/89388987-1215-42f8-a758-497f3475f52e" />

[View Experiment 13 Details] https://github.com/EmmanAbad/Laboratory-Midsommar/blob/main/EXPERIMENT%2013%20-%20PCM%20Decoding.md

</details>

---
<details>
<summary> EXPERIMENT 14: Bandwidth Limiting and Restoring Digital Signals</summary>

**INTRODUCTION**
* Demonstrates how transmission media (wires or fiber) act as filters that distort digital signals by removing their high-frequency harmonics.

**EXPLANATION**
* When bandwidth is restricted, sharp digital pulses become rounded, causing Inter-Symbol Interference. This experiment shows how a comparator can "square up" these distorted waves to restore clear logic levels for the receiver.

**WAVEFORM RESULT EXAMPLE**
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/75614157-3f98-4d61-b7aa-9787ff6f8495" />

[View Experiment 13 Details] https://github.com/EmmanAbad/Laboratory-Midsommar/blob/main/EXPERIMENT%2014%20-%20Bandwidth%20Limiting%20and%20Restoring%20Digital%20Signals.md

</details>

---

### Learnings: 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The primary learning across these modules is the critical role of synchronization and physical constraints. Digital systems like PCM offer superior noise resistance but are entirely dependent on precise timing (Clock and Frame Sync). Furthermore, the fidelity of any communication system is bound by the Nyquist Rate (for sampling) and the Channel Bandwidth (for transmission), both of which dictate the maximum speed and quality of data transfer.
</p>

---

### Conclusions:
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;It is concluded that while digital transmission systems are more complex than analog ones, they are far more reliable for modern communication because they can be "restored" and filtered more effectively. Success in telecommunications requires a balance between the bit-rate of the message and the bandwidth of the channel; if the channel is too narrow or the sampling is too slow, aliasing and distortion will occur. Ultimately, the use of low-pass filtering remains the universal "bridge" used to return modulated or sampled data back into a human-readable analog format.
</p>
