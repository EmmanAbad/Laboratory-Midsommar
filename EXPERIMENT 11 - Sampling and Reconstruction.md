# EXPERIMENT 11 - Sampling and Reconstruction :page_facing_up: 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Digital transmission is rapidly replacing analog methods in modern commercial applications because of its superior ability to resist interference from electrical noise. While many different digital systems exist for various purposes they all require that analog information such as speech or music be converted into a digital format before transmission. This conversion process relies on sampling where the voltage of the analog signal is measured at specific regular intervals.

&nbsp;&nbsp;&nbsp;&nbsp;Figure 1a illustrates a message consisting of a pure sinewave alongside the digital sampling signal used to trigger measurements. The resulting waveform shows natural sampling where the sample follows any voltage changes occurring during the measurement period. Some digital systems cannot function with these changing samples so an alternative approach is used as seen in Figure 1b. This method is known as sample and hold or pulse amplitude modulation and it ensures the sample size remains fixed at the exact moment the signal is measured.
</p>

<img width="558" height="359" alt="image" src="https://github.com/user-attachments/assets/0403fbf0-ef52-4523-b48a-7e4fb01ed54e" />

---

### Introduction 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Modern communication systems are increasingly shifting from analog to digital transmission because digital signals are far more effective at resisting interference from electrical noise. While information such as speech or music starts as an analog signal it must be converted to a digital format through a process called sampling. This involves measuring the analog signal's voltage at regular intervals to create a discrete representation. Techniques such as natural sampling and sample and hold schemes are used to capture these measurements with the latter being essential for systems where changing sample voltages are unacceptable.
</p>

---

### Objectives
* Implement both natural sampling and sample and hold techniques using the Emona Telecoms-Trainer 101 equipment.
* Demonstrate the process of message reconstruction by using a tuneable low pass filter to recover a sinewave from a sampled signal.
* Analyze the spectral composition of sampled signals to understand why a message can be recovered from discrete measurements.
* Investigate the phenomenon of aliasing and how it distorts the reconstructed signal when the sampling frequency is too low.
* Determine the theoretical minimum sampling frequency required for a 2kHz sinewave and compare it to actual experimental results.
* Observe how sampling and reconstruction principles apply to complex audio signals like speech and humming.

---

### Equipment
* Emana Telecoms-Trainer 101 (plus power-pack)
* Dual channel 20MHz oscilloscope
* two Emano Telecoms Trainer 101 oscilloscope leads
* assorted Emona Telecoms-Trainer 101 patch leads

---

**Procedure – Part A: Sampling a Sample Message**
1. Gather the required trainer components and ground the oscilloscope leads into a (GND) socket.
2. Connect the Master Signals 2kHz SINE output to the Dual Analog Switch input, using the 8kHz DIGITAL output as the control signal.
3. Set the Trigger Source to CH1 (or INT) and the Mode to CH1.
4. Adjust the Timebase to display two cycles of the 2kHz sine wave and set Vertical Attenuation to 1V/div.
5. Switch the scope Mode to DUAL to view both the original message and the sampled output simultaneously.
6. Draw the two resulting waveforms to scale, ensuring enough space remains for a third waveform later.
7. Modify the existing circuit by replacing the electronically controlled switch with a sample and hold module while keeping the 2kHz sine wave and 8kHz pulse train as the message and sampling signals.
8. Use the remaining space on the graph paper to draw the new sample and hold message to scale.

**Procedure – Part B: Sampling Speech**
1. Disconnect the 2kHz sine output and connect the speech module output to the circuit input.
2. Change the timebase to 2ms/div to accommodate the complexity of audio signals.
3. talk, sing, or hum into the microphone to observe how speech is converted into discrete samples.

**Procedure – Part C: Reconstructing a Sampled Message**
1. Set Timebase to $0.1\text{ ms/div}$
2. Set Gain to middle and Cut-off Frequency fully anti-clockwise.
3. Disconnect Speech module; connect S/H output to Filter input (per Figure 7).
4. Connect Ch. 1 to the original message and Ch. 2 to the Filter output.
5. Slowly turn the Cut-off control clockwise until the message signal reappears on the scope.

**Procedure – Part D: Aliasing**
1. Set the VCO module's Frequency Adjust control fully clockwise.
2. Set the Range control to the LO position.
3. Update the set-up as shown in Figure 9, using the VCO module to provide a variable sampling frequency to the S/H control input.

**Waveforms Results**
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/a0145970-1771-4058-b04f-f42f1c7b8281" />

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/3b775d00-812f-4097-a013-8ae06cfabd6f" />

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/f7dfa261-ab91-4934-96f7-7f2408d5a89c" />

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/fe64918c-945e-4578-8a11-7a3176b5bcda" />

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/0edf1004-14b0-4050-ac04-628c51a6cef7" />

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/de441582-4521-4052-90d7-28f3854acb7d" />



https://github.com/user-attachments/assets/54ed6d04-ab21-4dd7-810b-869b987bcb91



**Learning**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This experiment demonstrates that digital communication depends on converting continuous analog signals into discrete samples and back again without loss of information. Through Parts A and B, it was observed that while natural sampling follows the message's voltage changes, the Sample and Hold (S/H) method is more effective for digital systems because it maintains a fixed voltage level for each interval.

&nbsp;&nbsp;&nbsp;&nbsp;The reconstruction process in Part C proved that these discrete samples still contain the original message's frequency; by using a Tuneable Low-pass Filter, the original sinewave can be isolated and recovered from the complex spectral components created during sampling. Finally, Part D highlighted the critical constraint of the Nyquist Criteria: if the sampling frequency (controlled via the VCO) drops below twice the message frequency, aliasing occurs. This creates irreversible distortion in the reconstructed signal, confirming that a sufficiently high sampling rate—exceeding the theoretical minimum to account for real-world filter limitations—is essential for accurate communication.
</p>

---

### Questions and Answers 
**Question 1 — What type of sampling is shown in Figure 1a?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Natural Sampling, because when the sampling switch remains closed for a finite duration, allowing the output to follow the continuous voltage changes of the message signal. Because the switch is active for a specific interval, the resulting pulse tops are curved and directly reflect the original analog shape. The signal then returns to zero between these pulses in coordination with the sampling clock.
</p>

**Question 2 — What two features of the sampled signal confirm this?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The first feature is that the tops of the samples are not flat but follow the curve of the original message signal. The second feature is that the signal returns to zero volts between each sample pulse.
</p>

**Question 3 — What two features confirm the sample-and-hold scheme?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The waveform features flat-topped pulses, indicating the signal value is held constant between intervals. Additionally, the signal amplitude remains fixed at the moment of sampling rather than continuously following the input waveform.
</p>

**Question 4 — What is the name of the distortion observed when the sampling frequency is too low?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This distortion is known as aliasing.
</p>

**Question 5 — For a 2 kHz message, what is the theoretical minimum sampling frequency?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;According to the Nyquist Criteria, the rate must be at least twice the highest frequency, which is 4 kHz.
</p>

**Question 6 — Why is the actual minimum sampling frequency higher than the theoretical minimum?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Real-world filters do not have an instantaneous "brick wall" cut-off; their attenuation is gradual. A higher sampling rate provides a necessary margin to prevent higher frequency harmonics from bleeding into the reconstructed message.
</p>

---

### Learnings
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The experiment provided a clear look at how analog signals are turned into digital formats through sampling and then back again. It was observed that natural sampling captures the signal voltage as it changes while the sample and hold method keeps the voltage level steady for the duration of the sample. Using a low pass filter proved that an original message can be recovered from a sampled signal because the sampling process naturally preserves the original frequency component among many others. The most important part was seeing what happens when the sampling frequency is lowered too much. This led to aliasing where the reconstructed signal became distorted and did not look like the original message anymore. It was confirmed that the sampling rate must be at least twice the highest frequency of the message to avoid this issue.
</p>

---

### Conclusion
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This laboratory session demonstrated that digital transmission systems are superior to analog ones because they handle noise and interference much better. By testing both natural and pulse amplitude modulation it was shown that discrete samples contain all the necessary data to rebuild the original analog waveform. The use of a tuneable low pass filter successfully isolated the message frequency from the complex spectral components created during the sampling stage. However the results also proved that the sampling rate is a critical factor in communication. If the rate drops below the Nyquist minimum the signal cannot be reconstructed accurately due to aliasing distortion. Overall the experiment verified the theoretical foundations of digital sampling and reconstruction which are essential for modern telecommunications.
</p>

