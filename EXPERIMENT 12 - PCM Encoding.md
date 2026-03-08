# EXPERIMENT 12 - PCM Encoding :page_facing_up: 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Digital transmission systems have largely replaced analog methods in the telecommunications industry which makes understanding pulse code modulation a necessity for technical professionals. PCM functions by converting analog message signals into a serial stream of binary digits through a process known as encoding. This procedure involves sampling the analog voltage at regular intervals and comparing those samples to specific reference voltages called quantisation levels. The system then assigns the closest level to the sample and outputs the corresponding binary number one bit at a time. The encoder clock frequency is a critical performance factor because it must be at least twice the message frequency to prevent aliasing during sampling. Another significant concern is quantisation error which occurs when the original sample value is lost because it does not perfectly match a quantisation level. Since the receiver cannot recover the exact original voltage this error is reproduced during decoding. Increasing the number of quantisation levels can minimize this effect by reducing the gap between the sample and the reference voltage.
</p>

<img width="461" height="191" alt="image" src="https://github.com/user-attachments/assets/af57e8af-6e6c-46eb-bb79-194e2436643d" />

---

### Introduction 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This experiment investigates the fundamentals of Pulse Code Modulation (PCM) through the use of the Emona Telecoms-Trainer 101. The primary objective is to observe the conversion of analog signals into a digital format by sampling, quantizing, and encoding various input voltages. By analyzing both static DC and dynamic signals, the study aims to evaluate the accuracy of the 8-bit encoding process and the impact of quantisation error on signal integrity. This provides a practical foundation for understanding how digital transmission systems maintain data fidelity in modern telecommunications.
</p>

---

### Objectives
* Investigate the operation of a Pulse Code Modulation (PCM) encoder using the Emona Telecoms-Trainer 101.
* Observe the conversion of analog message signals into a serial stream of binary digits through the encoding process.
* Evaluate the impact of quantization levels and the encoder's clock frequency on signal accuracy.
* Determine the specific voltage range of the 8-bit encoder by identifying the maximum and minimum binary codes.
* Identify the causes and effects of quantization error during the digitization of analog signals.

---

### Equipment
* Emana Telecoms-Trainer 101 (plus power-pack)
* Dual channel 20MHz oscilloscope
* two Emano Telecoms Trainer 101 oscilloscope leads
* assorted Emona Telecoms-Trainer 101 patch leads

---

**Procedure – Part A: Static DC Encoding**
1. Gather the necessary equipment including the Emona Telecoms-Trainer 101 and a dual channel 20MHz oscilloscope.
2. Set the oscilloscope trigger source to Channel 1 and the PCM Encoder module to PCM mode.
3. Connect the encoder to an 8kHz digital clock signal from the Master Signals module.
4. Apply a 0V DC input to the encoder and monitor the Frame Synchronisation (FS) signal on the scope to stabilize the display.
5. Adjust the scope timebase to 0.1ms/div and use dual mode to view the clock input and FS output simultaneously.
6. Observe the 10-bit data output to identify the specific bit pattern associated with a zero-volt input.

<img width="342" height="234" alt="image" src="https://github.com/user-attachments/assets/7b0866a8-4064-4e83-bcea-932e7be49644" />

<img width="358" height="244" alt="image" src="https://github.com/user-attachments/assets/a5b8e839-fd7f-4353-b7e4-619a075b42d0" />

**Procedure – Part B: Variable DC Encoding**
1. Connect a Variable DCV module to the PCM Encoder input.
2. Establish a zero-volt reference by aligning the Channel 1 trace with a horizontal line on the scope.
3. Increase the DC voltage by turning the control clockwise until the output reaches the maximum code of 11111111.
4. Decrease the voltage by turning the control anti-clockwise until the output reaches the minimum code of 00000000.
5. Measure and record these boundary voltages in Table 1 to determine the encoder's peak-to-peak amplitude capacity.

<img width="340" height="233" alt="image" src="https://github.com/user-attachments/assets/1100d701-5655-4664-9993-75be826f7007" />


**Procedure – Part C: Quantisation Analysis**
1. Set the Variable DC control to approximately the middle of its travel range.
2. Move the control slightly left and right to observe if the output code remains unchanged for a range of sample voltages.
3. Calculate the voltage difference between quantization levels by dividing the total measured range from Table 1 by 256.

**Procedure – Part D: Continuously Changing Voltages**
1. Replace the DC source with a Voltage Controlled Oscillator (VCO) to provide a dynamic sinewave input.
2. Configure the VCO to provide the encoder with a 50kHz clock signal.
3. Set the oscilloscope timebase to 50µs/div to monitor the resulting PCM data output.
4. Observe how the binary stream changes in real-time as the analog input fluctuates over time.

**Waveform Result**
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/61a240aa-870c-4396-9814-42b4434148e8" />

**Learning**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The experiment involving the Emona Telecoms-Trainer 101 demonstrated that Pulse Code Modulation effectively digitizes analog signals by mapping sampled voltages to specific 8-bit binary codes. Observations of the Frame Synchronisation (FS) signal on the oscilloscope were essential for defining the start of each 10-bit data frame and correctly identifying the bit patterns. When the input was set to 0V DC, the encoder produced a mid-range binary value rather than 00000000, as the minimum code is reserved for the most negative voltage of approximately -2V. The waveforms captured during the variable DC and VCO procedures showed that the binary output fluctuates in real-time to track amplitude changes, though it is subject to quantization error when a sample falls between the system's 256 discrete levels. This error manifests as bit-toggling in the LSB and highlights the trade-off between the number of quantization levels and signal fidelity.
</p>

---

### Questions and Answers 
**Question 4 — What is the binary number that the PCM Encoder module is outputting?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;For a 0V DC input, the encoder typically outputs a code representing the mid-point of the range, often 10000000 or similar depending on the codec offset.
</p>

**Question 5 — Why does the code change even though the input voltage is steady?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Small noise fluctuations or clock instability can cause the sample to toggle between two adjacent quantization levels.
</p>

**Question 6 — Why does the PCM Encoder module output this code for 0V DC and not 00000000?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The system maps 00000000 to the most negative voltage (-2V) so 0V must be represented by a mid-range binary value.
</p>

**Question 7 — What happens to the Variable DC module's output?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The DC voltage increases as the control is turned clockwise.
</p>

**Question 8 — In what way does the binary number change?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The binary value increases towards the maximum 8-bit value of 11111111.
</p>

**Question 9 — What happens to the Variable DC module's output?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The DC voltage decreases as the control is turned anti-clockwise.
</p>

**Question 10 — What happens to the binary number that the PCM Encoder module is outputting?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The binary output decreases towards the minimum value of 00000000.
</p>

**Question 11 — Maximum allowable amplitude (peak-to-peak)?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The total range from -2V to +2V results in a 4V peak-to-peak capacity.
</p>

**Question 12 — Name for the difference between a sampled voltage and its closest level?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This is defined as quantisation error.
</p>

**Question 13 — Calculate the difference between levels.**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Dividing the 4V range by 256 codes gives roughly 15.6mV per level.
</p>

**Question 14 — To reduce quantization error it is better to have:**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;More quantisation levels between ±2V.
</p>

| PCM Encoder's output code | PCM Encoder's input voltage |
| --- | --- |
| 11111111 | +2.0V (APPROX) |
| 00000000 | -2.0V (APPROX) |

---

### Learnings
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The lab work showed that PCM encoding is highly dependent on both the sampling rate and the resolution of quantization levels. It was observed that even with a steady DC input, the output bits can fluctuate if the signal sits right on the edge of two levels. Understanding the role of the Frame Synchronisation signal proved vital for correctly reading the serial data on an oscilloscope. Furthermore, it became clear that the 8-bit limitation of the codec chip defines the precision of the entire system.
</p>

---

### Conclusion
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This experiment demonstrated that PCM encoding is the standard for digitizing analog signals through sampling and quantization. It was found that 8-bit systems provide 256 discrete levels which inherently limits the resolution of the signal. Any discrepancy between the actual sample and the assigned level results in quantization error that cannot be corrected later. The testing showed that the encoder's clock must be at least twice the message frequency to avoid aliasing. In summary, PCM provides a robust transmission method but its fidelity depends heavily on the density of quantization levels and the sampling rate used during the encoding stage.
</p>

