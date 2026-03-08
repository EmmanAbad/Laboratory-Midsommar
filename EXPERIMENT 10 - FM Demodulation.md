# EXPERIMENT 10 - FM Demodulation :page_facing_up: 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The Zero-Crossing Detector recovers messages from FM signals by first passing the input through a comparator to create a heavily clipped square wave. This square wave triggers the ZCD to generate a series of pulses with a fixed duration every time the signal crosses zero volts. Because these pulses have a constant "mark" time, any change in the FM signal's frequency directly alters the signal's duty cycle (mark/space ratio). As shown in the block diagram, this pulse train is then passed through a low-pass filter, which smooths the varying duty cycle to reconstruct the original demodulated message.
</p>

<img width="296" height="273" alt="image" src="https://github.com/user-attachments/assets/fac7208e-d280-404f-b198-199d13331f54" />

<img width="401" height="107" alt="image" src="https://github.com/user-attachments/assets/596d4b55-ab3f-453b-9577-8966832ba748" />

---

### Introduction 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;FM demodulation is the process of recovering a message signal (such as a DC voltage, sinewave, or speech) from a carrier wave whose frequency has been varied. While several methods exist—including slope detectors, Foster-Seeley discriminators, and Phase-Locked Loops (PLL)—this experiment focuses on the zero-crossing detector. This method works by converting an FM sinewave into a squarewave via a comparator and then using a ZCD to generate pulses of fixed duration for every zero-crossing. Because these pulses have a fixed "mark" time, changes in the FM signal’s frequency result in changes to the "space" between pulses, effectively varying the duty cycle. A low-pass filter (LPF) is then used to extract the changing DC component, which serves as a copy of the original message.
</p>

---

### Objectives
* Use the Emona Telecoms-Trainer 101 to generate an FM signal using a Voltage Controlled Oscillator (VCO).
* Set up a zero-crossing detector circuit to recover a message from an FM signal.
* Verify the operation of the ZCD by observing variations in message amplitude and frequency.
* Demonstrate the successful transmission and recovery of complex signals, including sinewaves and human speech.

---

### Equipment
* Emana Telecoms-Trainer 101 (plus power-pack)
* Dual channel 20MHz oscilloscope
* two Emano Telecoms Trainer 101 oscilloscope leads
* assorted Emona Telecoms-Trainer 101 patch leads
* one set of headphones (stereo)

---

**Procedure – Part A: Setting up the FM Modulator**
1. Initialize the VCO module with Gain fully clockwise, Frequency Adjust at the midpoint, and Range set to "LO".
2. Calibrate the VCO to a 10kHz rest frequency by adjusting the signal period to $100\mu s$ on the oscilloscope.
3. Connect a Variable DCV module to the VCO to act as a simple DC message.
4. Adjust the VCO sensitivity (Gain) so that a +2V input results in a 15kHz output ($66\mu s$ period) and a -2V input results in approximately 5kHz.

<img width="338" height="166" alt="image" src="https://github.com/user-attachments/assets/b1de1da1-e506-4c51-98b5-89c9a5ff081d" />

**Procedure – Part B: Setting up the Zero-Crossing Detector**
1. Configure the Twin Pulse Generator by turning both Width and Delay controls fully anti-clockwise.
2. Connect the Master Signals 100kHz digital output to the ZCD clock to establish a timing reference.
3. Switch the oscilloscope timebase to 2µs/div to accurately view short-duration pulses.
4. Adjust the Width control until the output pulse duration is exactly 12µs.
5. Reset the scope timebase to 50µs/div to prepare for viewing the modulated signal.

<img width="422" height="357" alt="image" src="https://github.com/user-attachments/assets/7ed5756f-9bc7-4d49-aada-da875225c8f8" />

**Procedure – Part C: Investigating the ZCD Operation**
1. Pass the FM signal through the Utilities module comparator to convert the sinewave into a squared-up signal.
2. Feed the comparator output into the ZCD to trigger the $12\mu s$ pulses on every positive zero-crossing.
3. Connect the ZCD output to the Baseband LPF on the Channel Module to extract the message.
4. Vary the Variable DCV control and observe the resulting change in the ZCD signal’s duty cycle.
5. Confirm that the DC voltage at the LPF output tracks the movement of the Variable DCV knob.

<img width="413" height="160" alt="image" src="https://github.com/user-attachments/assets/1600fbbc-bf2b-467a-8ac2-d5c1c2657812" />

<img width="427" height="228" alt="image" src="https://github.com/user-attachments/assets/08b8e846-a70e-4cfb-b5d3-89c9211985f7" />

<img width="482" height="204" alt="image" src="https://github.com/user-attachments/assets/7cf57d80-40c4-489c-8b09-8d47ec98b793" />

**Procedure – Part D: Transmitting and Recovering a Sinewave**
1. Replace the Variable DCV module with a 2kHz sinewave from the Master Signals module.
2. Monitor the original 2kHz message on Channel 1 and the demodulated LPF output on Channel 2.
3. Observe the "breathing" effect of the ZCD pulse train as it expands and contracts with the 2kHz frequency.
4. Verify that the output of the LPF is a clean reconstruction of the input 2kHz sinewave.

<img width="348" height="147" alt="image" src="https://github.com/user-attachments/assets/f1c8ab15-0203-430c-9ee2-c3f03c813713" />

**Procedure – Part E: Transmitting and Recovering Speech**
1. Connect a speech source to a Tuneable LPF to limit the signal bandwidth to 2kHz.
2. Modulate the VCO with the filtered speech signal to create a complex FM signal.
3. Connect the demodulated LPF output to the Buffer module to amplify the signal for audio output.
4. Use headphones to listen to the recovered speech and verify its clarity and accuracy.

**Waveforms Results**
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/5ece5881-a3e4-43a2-ac05-98cd41fefbbf" />

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/d93826f5-ca5c-441b-a76f-db4b0e3cf033" />

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/822e3ebf-be6e-434a-9ed9-17ef403b728a" />



https://github.com/user-attachments/assets/927992c0-5f2b-4b20-8345-a7d285fab6b9



**Learning**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Through the systematic execution of this experiment, I learned that successful FM demodulation using a Zero-Crossing Detector (ZCD) relies on a precise chain of signal transformations. In the initial stages, I discovered the importance of linear modulation, where calibrating the VCO to a specific rest frequency and sensitivity ensures that message amplitudes are accurately mapped to frequency deviations. Setting up the ZCD taught me that the "information" in this specific system is encoded into the duty cycle; by maintaining a strictly fixed pulse width (mark time), the varying frequency of the carrier is forced to change only the "space" between pulses. I observed that the comparator is a critical intermediary that strips away amplitude variations to provide clean digital edges for the ZCD. Finally, through the transmission of sinewaves and speech, I learned that a Low-Pass Filter acts as a crucial integrator that extracts the average DC value of the pulse train, effectively smoothing the high-frequency switching into a continuous, audible, and accurate reconstruction of the original baseband signal.
</p>
---

### Questions and Answers 
**Question 1 — Why is the FM signal no-longer a sinewave?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The FM signal is no longer a sinewave because it has been passed through a comparator on the Utilities module, which heavily clips the signal to convert it into a squarewave.
</p>

**Question 2 — What type of waveform does the Comparator output?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The comparator outputs a squarewave (or pulse train) that switches between high and low levels at every zero-crossing of the input signal.
</p>

**Question 3 — What does this tell us about the DC component of the comparator's output?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This tells us that the DC component of the comparator’s output is constant. Since the squarewave has a fixed 50% duty cycle, its average value does not change even if the frequency of the FM signal changes.
</p>

**Question 4 — What type of waveform does the ZCD output?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The Zero-Crossing Detector (ZCD) outputs a rectangular wave consisting of a series of pulses with a fixed "mark" (duration) time.
</p>

**Question 5 — As the FM signal changes frequency so does the ZCD's output. What aspect of the signal changes to achieve this?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;To achieve this change in frequency while keeping the mark time fixed, only the "space" (the duration between pulses) changes, which in turn changes the overall duty cycle of the signal.
</p>

**Question 6 — What does this tell us about the DC component of the [ZCD] output?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;It tells us that the DC component of the ZCD output is variable. Because the pulse width is fixed but the frequency varies, the average voltage (DC level) changes in direct proportion to the input frequency.
</p>

**Question 7 — If the original message is a sinewave instead of a variable DC voltage, what would you expect to see out of the Baseband LPF?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;You would expect to see a reconstructed sinewave that matches the frequency and shape of the original message signal used at the modulator.
</p>

**Question 8 — What does the FM modulator's output signal tell you about the ZCD signal's duty cycle?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The FM modulator's output frequency determines the rate of the pulses; a higher frequency results in more pulses per second, which increases the ZCD signal's duty cycle.
</p>

---

### Learnings
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Through this experiment, I learned that FM demodulation via zero-crossing detection is a multi-stage process that relies heavily on the relationship between frequency and duty cycle. I discovered that a comparator is necessary to "square up" the FM signal, providing the sharp edges required to trigger the pulse generator. A key takeaway was understanding that by keeping the pulse width (mark) constant, the average DC value of the pulse train becomes directly proportional to the frequency of the input signal. I also observed the critical role of the Low-Pass Filter, which effectively "smooths" the high-frequency pulses to reconstruct the original baseband message, whether that message is a simple DC level or complex human speech.
</p>

---

### Conclusion
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The experiment successfully demonstrated the principles of FM demodulation using the Emona Telecoms-Trainer 101. By following the systematic procedures from Part A to E, I was able to observe how a frequency-modulated carrier is progressively transformed back into its original message form. The zero-crossing detector proved to be an effective demodulator, capable of handling various signal types with high fidelity. In conclusion, the setup confirmed that as long as the pulse width is shorter than the period of the highest frequency in the FM signal, the original information can be accurately recovered through duty cycle variations and low-pass filtering.
</p>
