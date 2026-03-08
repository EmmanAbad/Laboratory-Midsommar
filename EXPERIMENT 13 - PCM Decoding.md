# EXPERIMENT 13 - PCM Decoding :page_facing_up: 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Pulse Code Modulation show that recovering an original message from a serial binary stream requires precise synchronization and voltage reconstruction. The process involves extracting binary numbers from each frame to generate a proportional voltage, which is held to form a pulse amplitude modulation (PAM) signal. Final reconstruction is achieved by passing this PAM signal through a low-pass filter to smooth the transitions. Accuracy depends heavily on the decoder clock frequency matching the encoder's clock, as any discrepancy causes bits to be read twice or missed entirely.

&nbsp;&nbsp;&nbsp;&nbsp;Such timing errors result in incorrectly interpreted voltages that may become audible if they occur frequently enough. Frame synchronization remains a critical challenge that is managed by either using a separate synchronization signal or embedding a specific code within the data stream. While a separate signal ensures the decoder identifies the start of a frame, it requires additional transmission resources. Failure to maintain this synchronization causes every numerical value to be misinterpreted, which compromises the integrity of the decoded output.
</p>

---

### Introduction 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This experiment explores the process of Pulse Code Modulation (PCM) decoding, which is the recovery of an original analog message from a serial stream of binary numbers. Because simple decoding systems rely on precise timing, this lab demonstrates the necessity of clock and frame synchronization. You will use the Emona Telecoms-Trainer 101 to convert PCM data back into a Pulse Amplitude Modulation (PAM) signal and finally reconstruct the original message using low-pass filtering.
</p>

---

### Objectives
* To understand the fundamental steps of PCM decoding: frame identification, binary extraction, voltage generation, and signal reconstruction.
* To observe the critical role of clock frequency and frame synchronization in correctly interpreting transmitted bits.
* To demonstrate message recovery by passing a PAM signal through a Tuneable Low-pass Filter.
* To perform a subjective comparison between the original message and the reconstructed version using both visual (oscilloscope) and audible (headphones) methods.

---

### Equipment
* Emana Telecoms-Trainer 101 (plus power-pack)
* Dual channel 20MHz oscilloscope
* two Emano Telecoms Trainer 101 oscilloscope leads
* assorted Emona Telecoms-Trainer 101 patch leads

---

**Procedure – Part A: Setting up the PCM encoder**
1. Gather the required equipment, including the Emona Telecoms-Trainer 101, oscilloscope, and leads.
2. Set the oscilloscope's Trigger Source to CH1 (or INT) and the Mode to CH1.
3. Set the Mode switch on the PCM Encoder module to the PCM position.
4. Connect the Master Signals module's 100kHz DIGITAL output to the CLK input of the PCM Encoder.
5. Connect the Variable DCV module's VDC output to the INPUT 1 of the PCM Encoder.
6. Connect the encoder's FS output to CH1 of the scope and the PCM DATA output to CH2.
7. Adjust the scope's Slope to "-" and the Timebase to 10µs/div to view one pulse of the FS output.
8. Vary the Variable DC control and observe the PCM DATA output bits changing on the oscilloscope.

<img width="368" height="223" alt="image" src="https://github.com/user-attachments/assets/7a5e0d62-a147-424a-b94e-546b5a06d683" />

<img width="416" height="254" alt="image" src="https://github.com/user-attachments/assets/2f4b69f6-ec3e-4512-a852-121cd4d0f165" />

**Procedure – Part B: Decoding the PCM data**
1. Return the oscilloscope's Slope control to the "+" position and the Mode to CH1.
2. Connect the encoder's PCM DATA output to the PCM DATA input of the PCM Decoder module.
3. "Steal" the clock by connecting the encoder's CLK input to the decoder's CLK input.
4. "Steal" the frame synchronization by connecting the encoder's FS output to the decoder's FS input.
5. Set the scope's Mode to DUAL to compare the original message (at the encoder input) with the PCM Decoder module's output.
6. To hear the signal, connect the PCM Decoder output to the Buffer module's input and listen through headphones.
7. Observe the "stepped" nature of the reconstructed signal.

<img width="432" height="248" alt="image" src="https://github.com/user-attachments/assets/04333443-42af-429b-bcfa-de6be2df47ed" />

**Procedure – Part C: Encoding and decoding speech**
1. Remove the Buffer module and disconnect the VCO or DC inputs from the encoder.
2. Connect the Speech module's output to the PCM Encoder's input.
3. Talk, sing, or hum into the microphone while watching the oscilloscope display the resulting PCM data.

**Procedure – Part D: Recovering the message**
1. Set the Tuneable Low-pass Filter module's Gain to the middle of its travel and the Cut-off Frequency fully anti-clockwise.
2. Disconnect the Speech module and reconnect the VCO SINE output to the encoder input.
3. Connect the PCM Decoder's output to the input of the Tuneable Low-pass Filter.
4. Connect the output of the filter to CH2 of the oscilloscope.
5. Slowly turn the filter's Cut-off Frequency clockwise until the original smooth message signal is reconstructed on the scope.
6. Connect the headphones to the filter's output via the Buffer module to compare the sound of the reconstructed signal to the original.

<img width="482" height="206" alt="image" src="https://github.com/user-attachments/assets/dfe57821-76fa-4bb0-8270-da61e8853d8e" />


**Waveform Result**
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/4430e6ac-ee57-4477-9556-51deb46ee0c9" />

**Learning**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The experiment across Parts A through D demonstrates the complete lifecycle of a Pulse Code Modulation (PCM) signal, from digital encoding to analog reconstruction. In Part A, we learned that converting a message into PCM requires a precise $100\text{ kHz}$ digital clock and produces a unique serial binary stream that changes in real-time as the input voltage varies. Part B highlighted the absolute necessity of synchronization; the decoder cannot function without "stealing" the encoder's clock and frame synchronization ($FS$) signals to correctly interpret the data frames. When successfully decoded, the resulting raw signal is a "stepped" Pulse Amplitude Modulation (PAM) waveform, which we observed as a series of held voltage levels. Part C and Part D proved that while complex signals like speech can be digitized, the raw "stepped" output sounds distorted until it is processed. By passing this signal through a Tuneable Low-pass Filter, we successfully smoothed the transitions, removing high-frequency switching noise to reconstruct a clean analog message that visually and audibly resembles the original.
</p>

---

### Questions and Answers 
**Question 1 — What does the PCM Decoder’s "stepped" output tell you about the type of signal that it is?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;It indicates that the signal is a Pulse Amplitude Modulation (PAM) version of the original message. The "steps" occur because the decoder generates a voltage proportional to a binary number and holds that voltage until the next frame is decoded.
</p>

**Question 2 — Why do you think the PCM Decoder's clock and frame synchronisation signals are "stolen" from the PCM Encoder?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The PCM Decoder's clock and frame synchronisation signals are "stolen" from the PCM Encoder because the TIMS module is not self-clocking and cannot self-detect the beginning of each new 8-bit data frame. Without these shared signals, the decoder would misinterpret the serial data stream, reading bits twice or missing them entirely, which results in incorrect voltage outputs and audible errors. Consequently, the decoder must be physically synchronized with the encoder's $CLK$ and $FS$ outputs to accurately recover the original message.
</p>

**Question 3 — Even though the two signals look and sound the same, why isn't the reconstructed message a perfect copy of the original message?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The reconstructed message is not a perfect copy due to quantization error (or quantization noise). When the original analog signal was encoded, it had to be rounded to the nearest available binary level, leading to a slight permanent loss of detail that cannot be recovered during decoding.
</p>

---

### Learnings
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The experiment highlights that successful PCM decoding is entirely dependent on timing; without shared clock and frame synchronization signals, the data is incorrectly interpreted. It also clarifies that the raw output of a PCM decoder is a "stepped" PAM signal, which requires a low-pass filter to remove high-frequency components and return it to a smooth analog form.
</p>

---

### Conclusion
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;PCM decoding effectively recovers analog information from digital data, provided the transmitter and receiver are synchronized. While the reconstructed signal appears identical to the original on an oscilloscope after filtering, it is technically an approximation due to the inherent limitations of the encoding process. This lab successfully demonstrates the transition from serial binary data back to a recognizable audio signal.
</p>
