# EXPERIMENT 14 - Bandwidth Limiting and Restoring Digital Signals :page_facing_up: 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Transmission media like metal conductors, optical fiber, and free-space all possess a specific bandwidth that functions as a filter. This filter attenuates high frequency harmonics and shifts the phase of the sine waves that make up both analog and digital signals. When the channel bandwidth is too narrow, these distortions prevent a PCM decoder from accurately identifying logic levels, which results in a noisy recovered message. By building a PCM system with a low-pass filter on the Emona Telecoms-Trainer 101, the visual and auditory effects of this degradation can be analyzed on an oscilloscope. Using a comparator then demonstrates how a digital signal can be partially restored by re-establishing clear voltage thresholds.
</p>

<img width="372" height="163" alt="image" src="https://github.com/user-attachments/assets/07ee1fcc-7c6e-4c69-9a77-2e9dbd8bcab7" />

<img width="308" height="145" alt="image" src="https://github.com/user-attachments/assets/d8edb06a-f72b-41d0-bb60-c0aebdd41540" />

---

### Introduction 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;In the classical communications model, a message moves from a transmitter to a receiver over a channel. Every transmission medium has a specific bandwidth, which means it allows a range of signal frequencies to pass relatively unaffected while frequencies outside that range are attenuated. Digital signals are made up of many sinewaves called the fundamental and harmonics. If the channel's bandwidth is not wide enough, these harmonics are lost or attenuated, causing the digital signal to change shape and potentially leading to misinterpretation by receiver circuits like PCM decoders.
</p>

---

### Objectives
* To demonstrate how bandwidth limiting in a channel can distort digital signals and upset the operation of a receiver.
* To observe the specific effects of bandwidth limiting on PCM data using an oscilloscope and by listening to recovered audio messages.
* To analyze the relationship between a digital signal's bit rate and the channel's bandwidth requirements.
* To use eye diagrams as a tool to inspect and test the performance of a digital transmission channel.
* To implement a restoration method using a comparator to "clean up" or "square up" a bandwidth limited digital signal.

---

### Equipment
* Emana Telecoms-Trainer 101 (plus power-pack)
* Dual channel 20MHz oscilloscope
* two Emano Telecoms Trainer 101 oscilloscope leads
* assorted Emona Telecoms-Trainer 101 patch leads
* one set of headphones (stereo)

---

**Procedure – Part A: Bandwidth Limiting on PCM Decoding**
1. Set up a PCM communications system using a Variable DCV module, PCM Encoder, and PCM Decoder modules.
2. Introduce a Tuneable Low-pass Filter into the channel to model bandwidth limiting.
3. Vary the filter's cut-off frequency while observing the PCM Decoder's output for corruption.

<img width="404" height="216" alt="image" src="https://github.com/user-attachments/assets/432f6170-a711-4971-9687-29579bc4fdb5" />

<img width="482" height="224" alt="image" src="https://github.com/user-attachments/assets/3adf18c1-4db0-4730-b95d-bf3a1819713d" />

**Procedure – Part B: Effects on Digital Signal Shape**
1. Replace the DCV and PCM modules with a Sequence Generator to model a stable 32 bit digital data stream.
2. Monitor the digital signal before and after the Tuneable Low-pass Filter using a dual channel oscilloscope.
3. Gradually narrow the channel's bandwidth and observe the rounding and phase shifting of the digital pulses.
4. Use a VCO module to increase the transmission bit rate and observe how it produces the same distortion as reducing bandwidth.
5. Configure the oscilloscope for "eye diagram" mode by triggering from the system clock to evaluate signal quality.

<img width="439" height="215" alt="image" src="https://github.com/user-attachments/assets/5f541ddb-be1b-4dcd-bf47-9914b96b2804" />

<img width="476" height="220" alt="image" src="https://github.com/user-attachments/assets/1090ad0b-2666-4a70-8fad-39f949dcfdfb" />

**Procedure – Part C: Restoring Digital Signals**
1. Patch the distorted, bandwidth limited signal into one input of a comparator on the Utilities module.
2. Connect a Variable DCV to the other comparator input to act as a reference voltage.
3. Adjust the DC voltage to find the "right point" where the comparator produces a clean, squared up copy of the original signal.
4. Observe the limitations of this restoration when bandwidth is restricted too severely or when the reference voltage is incorrectly set.

<img width="488" height="236" alt="image" src="https://github.com/user-attachments/assets/dcf36815-e569-4439-b5af-df4bf161e2be" />


**Waveform Result**
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/37800aa3-aacb-4bc5-8727-9a93eb1caad2" />



https://github.com/user-attachments/assets/7c2c40b0-01ee-491c-8903-e9677b7f857c



**Learning**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The experimental procedures demonstrate that a digital signal is a complex waveform composed of a fundamental frequency and multiple high-frequency harmonics. Through Part A and Part B, it was learned that when a channel’s bandwidth is restricted using a low-pass filter, these essential harmonics are attenuated or lost, and the remaining components undergo phase shifting. This results in a visible rounding and distortion of the digital pulses on the oscilloscope, making it difficult for receiver modules like the PCM decoder to accurately identify logic levels and leading to noisy or incorrect data recovery. Part B specifically highlighted that increasing a signal's bit-rate has the same detrimental effect as reducing the channel's bandwidth, as both actions degrade the signal's shape relative to the available frequency range. Finally, Part C revealed that while bandwidth-limited signals can become severely distorted, they can be effectively restored using a comparator. By comparing the distorted signal against a stable DC reference voltage, the comparator amplifies the differences to produce a squared-up, clean copy of the original data, although a slight phase shift typically remains.
</p>

---

### Questions and Answers 
**Question 1 — Why does bandwidth limiting of the channel cause the PCM Decoder module to output incorrect voltages as well as the correct one?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Bandwidth limiting causes the PCM Decoder to output incorrect voltages because the loss of high frequency harmonics and phase shifting distorts the signal shape, causing codes to be misinterpreted.
</p>

**Question 2 — If this were a communications system transmitting speech, what would these errors sound like when the message is reconstructed?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;If this were a speech system, these errors would cause the recovered message to sound "noisy".
</p>

**Question 3 — What two things are happening to cause the digital signal to change shape? Tip: If you're not sure, see the preliminary discussion.**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The two things causing the shape change are the attenuation or loss of high frequency harmonics and the shifting of the phase of remaining sinewaves by different amounts.
</p>

**Question 4 — What other change to your communication system distorts the digital signal in the same way as increasing its bit-rate?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Increasing the transmission bit rate distorts the digital signal in the same way as reducing the channel's bandwidth.
</p>

**Question 5 — Although the restored digital signal is almost identical to the original digital signal, there is a difference. Can you see what it is?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;While the restored signal is almost identical to the original, it typically has a phase shift.
</p>

**Question 6 — Can this difference be ignored? Why?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This phase shift can often be ignored in this experiment, although it is noted that phase shifting can cause other problems for receivers in different contexts.
</p>

**Question 7 — Why do some DC voltages cause the comparator to output the wrong information?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;If the DC reference voltage is not adjusted to the correct point between the signal's swings, the comparator cannot accurately distinguish the logic levels.
</p>

**Question 8 — Why does the comparator begin to output the wrong information when this control is turned far enough?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The comparator outputs wrong information when the bandwidth is limited too far because the distortion becomes so severe that the signal no longer crosses the reference threshold reliably.
</p>

**Question 9 — How can the comparator restore the bandwidth limited digital signal when it is so distorted?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The comparator restores the signal by amplifying the difference between its inputs by a large amount, which produces a heavily clipped or "squared up" version of the distorted AC signal.
</p>

---

### Learnings
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The experiment demonstrates that digital signals are not just "on/off" pulses but are complex waveforms consisting of multiple frequencies. It becomes clear that the quality of data recovery is strictly dependent on the ratio between the signal's bit-rate and the channel's bandwidth. Using an eye diagram provides a visual representation of this quality; wide-open "eyes" indicate low distortion, while closing "eyes" signal degrading quality due to bandwidth limiting.
</p>

---

### Conclusion
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Bandwidth limiting is an inevitable challenge in digital communications that causes signal distortion through harmonic attenuation and phase shifting. While increasing bit-rates or narrowing bandwidth leads to corrupted data at the receiver, a comparator can effectively "clean up" or restore a distorted signal by squaring its edges, provided the distortion is not too extreme.
</p>
