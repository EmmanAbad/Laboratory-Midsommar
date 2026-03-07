# EXPERIMENT 9 - Frequency Modulation :page_facing_up: 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Amplitude modulation systems like AM, DSBSC, and SSB have a major drawback because they easily pick up electrical noise in the channel. This happens since noise affects the amplitude of the signal, which these systems rely on, so demodulators get disturbed by amplitude changes. Frequency modulation, on the other hand, varies the carrier frequency according to the message amplitude while keeping the carrier amplitude constant. FM demodulators respond to frequency changes, not amplitude, making FM less sensitive to noise and generally more reliable for communication. FM signals are generated using an oscillator whose frequency can be adjusted by an input voltage. When the input is zero, the oscillator runs at its rest or center frequency. If the voltage rises or falls, the output frequency shifts above or below this value, and larger input voltages produce greater frequency deviation.
</p>

<img width="367" height="272" alt="image" src="https://github.com/user-attachments/assets/d0b8fa00-3105-4d8e-81a9-c5744c38c3c9" />

---

### Introduction 
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;Frequency modulation systems provide a robust alternative to amplitude based methods like AM or DSBSC which often suffer from electrical noise interference. Since noise primarily impacts the amplitude of a signal, systems that rely on amplitude for data transmission are easily disrupted during the demodulation process. Frequency modulation avoids this issue by keeping the carrier amplitude constant while varying the frequency in response to the message signal amplitude. This characteristic makes FM demodulators naturally resistant to noise because they are designed to ignore amplitude fluctuations. The generation of these signals usually involves an oscillator where the output frequency shifts above or below a center value based on the input voltage levels.
</p>

---

### Objectives
* Demonstrate how a carrier frequency is modified by the voltage of a modulating message signal.
* Analyze the direct relationship between the message amplitude and the resulting frequency deviation of the FM signal.
* Evaluate the effect of message frequency on the rate at which the carrier swings around its center point.
* Compare the FM waveforms produced by different input sources including square waves and human speech.
* Observe the complex spectral composition of FM signals to confirm they contain many sine components regardless of the input type.
* Verify that FM remains more reliable for communication compared to standard amplitude modulation.

---

### Equipment
* Emona Telecoms-Trainer 101 (plus power-pack)
* Dual channel 20MHz oscilloscope
* Two Emona Telecoms-Trainer 101 oscilloscope leads
* Assorted Emona Telecoms-Trainer 101 patch leads

---

**Procedure – Part A: Frequency Modulating a Squarewave**
1. Gather all required equipment.
2. Set up the oscilloscope as in Experiment 1: Trigger Source to CH1 (or INT) and Mode to CH1.
3. On the VCO module, set Gain to ~2/3, Frequency Adjust to middle, and Range to LO.
4. Connect the circuit as in Figure 2, with the oscilloscope black lead in GND.
5. Set the scope Timebase to $\frac{1}{5*20μ}=10,000kHz$
6. Change Timebase to 0.1 ms/div to view ~10 sine cycles.
7. Modify the setup as shown in Figure 3, noting the new connection to the VCO output.

**Part A: Result**
<img width="1536" height="2048" alt="image" src="https://github.com/user-attachments/assets/8a048be8-88c7-48c9-a4b8-b4c5cbed589b" />
**Learning**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This section demonstrates the fundamental mechanism of a Voltage-Controlled Oscillator (VCO). It shows that the carrier frequency shifts above or below its center frequency in direct proportion to the high and low voltage levels of a squarewave input.
</p>

---

**Procedure – Part B: FM Signal with Speech**
1. Disconnect the Master Signals module 2 kHz DIGITAL output and connect to the Speech module output (Figure 5).
2. Set the oscilloscope Trigger Source to CH2.
3. Speak, sing, or hum while observing the display.
4. Adjust the Timebase to ~20 µs/div.
5. Hum quietly into the microphone and gradually increase volume without changing pitch, watching the FM waveform on the scope.

**Part B: Result**
<img width="1536" height="2048" alt="image" src="https://github.com/user-attachments/assets/e365fb4a-3a1c-4808-b88d-586fd78ca43b" />
**Learning**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This part highlights the proportional relationship between message amplitude and frequency deviation. By singing or humming into the microphone, you observe that increasing the volume (amplitude) results in a larger shift in the carrier frequency, while the pitch (frequency) of the voice determines how rapidly that shift occurs.
</p>

---

**Procedure – Part C: Spectral Composition of FM Signal**
1. Set the scope Mode to CH2 to view only the FM signal.
2. Disconnect the VCO input from the Speech module and modify the setup as in Figure 6.
3. If needed, turn the VCO Gain control slowly until the display shows the full range of sinewaves. Observe the highest, lowest, and intermediate frequencies.
4. Connect the VCO input to the Master Signals module 2 kHz DIGITAL output and note the spectral composition.
5. Connect the VCO input to the Speech module output and note the spectral composition.
6. Observe that the FM signal’s spectrum is complex regardless of the message waveform.

**Part C: Result**
<img width="1536" height="2048" alt="image" src="https://github.com/user-attachments/assets/b7f0d04f-e34e-495b-98f2-1cdd4a0d1e58" />
**Learning**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;This experiment focuses on the spectral composition of the FM signal, demonstrating that frequency modulation produces a signal rich in sinewave components. By observing the FM signal on the oscilloscope while switching between the 2 kHz digital signal and the Speech module output, the experimenter can see that the resulting spectrum remains complex regardless of whether the message waveform is a simple pulse or human voice. This phase emphasizes that the FM signal’s spectrum is inherently intricate and contains multiple frequencies across its highest, lowest, and intermediate ranges.
</p>

**Video Result** 


https://github.com/user-attachments/assets/906ae805-1ab6-42ad-8155-4c7cfe4f3e10


---

### Questions and Answers 
**Question 1 — Why does the frequency of the carrier change?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;In frequency modulation, the carrier’s instantaneous frequency is changed because the modulating (message) signal directly controls the frequency of the voltage‑controlled oscillator. As the message signal’s voltage varies, it causes the oscillator output to shift above or below its centre frequency in proportion to that voltage. This results in the carrier frequency changing according to the amplitude of the message.
</p>

**Question 2 — What is the relationship between the FM signal’s frequency deviation and the amplitude of the message?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The frequency deviation of the FM signal, which is how far the carrier frequency shifts from its centre value, increases as the amplitude of the message signal increases. In other words, a larger message amplitude causes a greater change in the FM output frequency.
</p>

**Question 3 — What is the relationship between the FM signal’s frequency deviation and the frequency of the message?**
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;While the maximum frequency deviation itself is ideally determined by the amplitude of the message, the rate at which the carrier frequency deviates above and below the centre frequency is tied to the message’s frequency. A higher message frequency means the carrier frequency will swing back and forth more rapidly. This relationship may not be easily observed with the present basic setup, but in theory the frequency of the message influences how often the deviation occurs per second.
</p>

---

### Learnings
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;The experiment showed that frequency modulation changes the carrier frequency according to the input message signal. The amplitude of the message affects how much the carrier frequency deviates. The frequency of the message controls how fast the carrier swings around its center. FM signals are less sensitive to amplitude noise than AM, DSBSC, or SSB signals which makes them more reliable for communication. The spectrum of FM signals is rich in sinewave components no matter if the input is a squarewave, digital signal, or speech. Using a voltage-controlled oscillator helped to see how real signals affect the carrier and how the modulation works in practice.
</p>

---

### Conclusion
<p align="justify">
&nbsp;&nbsp;&nbsp;&nbsp;FM provides better noise resistance compared to amplitude-based modulation systems. The carrier frequency deviation depends on the amplitude of the message signal while the frequency of the message determines the rate of change in the carrier. Observing FM waveforms demonstrated the complex spectral content of modulated signals. Controlling the amplitude and frequency parameters is needed to get proper modulation. The experiment reinforced how FM works in theory and in practice and showed why it is useful in communication systems.  
</p>
