TASK 1: Engineer’s Swiss Army Knife (MATLAB Onramp Course)
For this task, I successfully completed the MATLAB Onramp course and obtained the official certification. The module provided a hands-on introduction to the MATLAB environment, focusing heavily on the fundamentals of matrix and array manipulation, which is essential for handling discrete data. I learned core workspace commands, variable assignment, and how to utilize built-in mathematical functions. Additionally, the course covered comprehensive data visualization techniques, teaching me how to properly format and customize 2D plots. Mastering these foundational concepts—especially array operations and plotting tools—has been directly applicable to my subsequent tasks, allowing me to easily script and visualize linear convolutions using functions like subplot, stem, and plot.

<img width="1259" height="794" alt="Screenshot (696)" src="https://github.com/user-attachments/assets/858572b8-a85d-4bc5-984d-09fadf58030a" />


TASK 2: Cut, Pass, Repeat (Band Pass Filter)
A Band Pass Filter (BPF) allows signals within a specific frequency range to pass through while attenuating frequencies outside of that range. For this task, I designed a second-order active band pass filter using Operational Amplifiers in LTSpice.

The circuit parameters were carefully calculated and tuned to establish a lower cutoff frequency of 4kHz and an upper cutoff frequency of 10kHz. By selecting the appropriate resistor and capacitor values for the high-pass and low-pass stages, the OpAmp was configured to provide a voltage gain of approximately 1.5 within the passband. I verified the design by running an AC sweep analysis in LTSpice. The resulting Bode plot clearly demonstrated the expected frequency response, effectively filtering out the stopbands while hitting the targeted amplification between 4kHz and 10kHz.
<img width="1787" height="829" alt="Screenshot (701)" src="https://github.com/user-attachments/assets/75a62507-b3e1-43ec-ac35-320ffd154514" />

TASK 3: SPICEy Code
While GUI-based schematic capture is convenient, writing raw SPICE (Simulation Program with Integrated Circuit Emphasis) code is fundamental for VLSI design and understanding how simulators parse circuit netlists. For this task, I bypassed the schematic editor in LTSpice and wrote text-based SPICE code to define and simulate basic digital logic gates at the transistor level.
I implemented a CMOS Inverter, an AND gate, and an OR gate by explicitly defining the PMOS and NMOS transistor nodes, model parameters, voltage sources (Vdd and GND), and input pulse signals directly within the netlist. By running a transient analysis (.tran) on these text files, I verified the logic functionality of each gate. The resulting waveform plots accurately reflected the expected digital high and low states based on the input combinations.
OR GATE
<img width="1916" height="1009" alt="orgate" src="https://github.com/user-attachments/assets/8847f907-4e5b-46da-855a-4f5be7c85bbd" />
AND GATE
<img width="1920" height="1023" alt="AND" src="https://github.com/user-attachments/assets/d4067176-bcdc-4ace-8342-7f2ce959c788" />
INVERTER
<img width="1903" height="1013" alt="INVERTER" src="https://github.com/user-attachments/assets/631bb88d-422b-479a-80dd-7363829f7bd6" />

TASK 4: From Low to Woah! (Voltage Multiplier)
A voltage multiplier is a circuit that converts a lower DC voltage to a higher DC voltage using a network of capacitors and diodes driven by an oscillating signal. For this task, I designed a cascaded charge pump driven by a 555 Timer IC.

I configured the 555 Timer in astable mode to generate the continuous high-frequency square wave necessary to drive the pump. Starting with a standard 9V DC input, the square wave alternately charges and discharges the capacitors through the steering diodes. The first stage of the network acts as a voltage doubler, effectively shifting and adding the charge to produce an output of approximately 18V (accounting for minor diode voltage drops). By cascading a second multiplier stage directly onto the first, the pumping action is repeated, successfully stepping the final output voltage up to roughly 27V. I simulated the complete circuit to verify the step-up process across both stages.

<img width="1920" height="1007" alt="MULTIPLIER" src="https://github.com/user-attachments/assets/e67172ba-4310-439e-af43-a2bc97bea3f3" />

TASK 5: The Power Shuffle (Buck-Boost Converters)
DC-DC converters are essential power electronics circuits that efficiently step up or step down voltage levels using high-frequency switching, inductors, and capacitors. For this task, I simulated both a Boost and a Buck converter in LTSpice to demonstrate their distinct topologies and energy storage mechanisms.

Boost Converter (1.5V to 5V):
A boost converter steps up the input voltage to a higher output level. I designed a circuit to take a 1.5V DC input and boost it to a stable 5V.

This is achieved by rapidly switching a transistor. When the switch is closed, the inductor stores magnetic energy from the source. When it opens, the inductor's magnetic field collapses, adding its induced voltage to the source voltage and pushing current through a diode to charge the output capacitor to that higher 5V level.

Buck Converter (12V to 5V):
Conversely, a buck converter steps down the input voltage. I simulated a separate circuit to reduce a 12V DC input down to a 5V output.

In this configuration, closing the switch allows current to flow through the inductor to the load, storing energy. When the switch opens, the inductor releases its stored energy through a freewheeling diode to maintain a continuous, regulated lower-voltage current to the output capacitor and load.

<img width="1920" height="1014" alt="BUCK" src="https://github.com/user-attachments/assets/da98a2e8-d6bc-420f-8979-d727c25b5885" />
<img width="1920" height="1011" alt="Screenshot (703)" src="https://github.com/user-attachments/assets/76180179-b785-4e0a-9238-f987ec73c875" />

TASK 6: 4 Bits to Rule Them All (4-Bit ALU Design)The Arithmetic Logic Unit (ALU) is the core computational building block of any central processing unit. For this task, I designed and implemented a complete 4-bit ALU from scratch using basic logic gates in CircuitVerse.I began by constructing a 4-bit ripple-carry adder using individual full-adder modules. To handle subtraction, I implemented a 2's complement architecture. By using XOR gates on the second 4-bit operand and connecting the operation control line to the initial carry-in ($C_{in}$), the circuit seamlessly toggles between addition and subtraction without needing a separate subtractor block.Alongside the arithmetic block, I built parallel logical operation circuits to perform bitwise AND, OR, and XOR functions on the same 4-bit inputs. To tie it all together, I designed a Control Unit using a multiplexer. The control lines select which operation's result is passed to the final output display. I also ensured that the circuit correctly outputs the final carry and overflow flags to validate the arithmetic results.
<img width="1094" height="778" alt="alu" src="https://github.com/user-attachments/assets/fb89d556-f018-47e2-9a27-a719d1fe1573" />

TASK 7: Convolution Countdown (Digital Signal Processing)
Digital Signal Processing (DSP) relies heavily on understanding how mathematical operations manipulate discrete data. For the theoretical portion of this task, I studied the fundamentals of signals and systems, covering the distinctions between continuous-time and discrete-time signals. I also explored mathematical tools like the Z-Transform for analyzing discrete systems and the Fourier Transform for frequency-domain analysis.

For the practical implementation, I utilized MATLAB to perform and visualize the linear convolution of two 4-sample discrete signals. Convolution is a mathematical operation that expresses how the shape of one signal is modified by another, which is critical for understanding the output response of an LTI (Linear Time-Invariant) system.

I wrote a script defining the input sequences and utilized the built-in conv function to calculate the mathematical output. To properly document and visualize the transformation, I used the subplot command to cleanly organize the graphs. The stem function was particularly useful here for plotting the discrete data points of the input sequences and the final convolved output signal, allowing me to clearly see the discrete sample values.

![convol](https://github.com/user-attachments/assets/ce55a278-c9dd-42e9-8c99-85c3853d15cb)

TASK 8: Whose Array Is It Anyway? (Programmable Logic Devices)Programmable Logic Devices (PLDs) are essential for implementing custom combinational logic circuits efficiently. For this task, I studied the structural differences between Programmable Read-Only Memory (PROM), Programmable Array Logic (PAL), and Programmable Logic Arrays (PLA).The key distinction lies in their programmability: a PAL has a programmable AND array but a fixed OR array, making it faster but less flexible. A PLA features both a programmable AND array and a programmable OR array, offering maximum flexibility at the cost of slight propagation delays and complexity.To put this into practice, I designed a combinational logic circuit that outputs a '1' if the number of 1s in a 3-bit input (A, B, C) is odd. This effectively acts as an odd parity generator, which corresponds to the boolean expression:Y = A'B'C + A'BC' + AB'C' + ABCUsing Logisim Evolution, I implemented this logic twice:Using a PAL structure: I programmed the AND gates to generate the necessary product terms and routed them into the fixed OR gate connections.Using a PLA structure: I programmed both the AND array for the product terms and the OR array to sum the specific terms required for the output.
<img width="1272" height="818" alt="PLA" src="https://github.com/user-attachments/assets/6368568a-2193-4d41-b8d0-14af9f6fb8d5" />
<img width="1295" height="861" alt="Screenshot (686)" src="https://github.com/user-attachments/assets/141abb65-ba60-4640-b9d6-3193559e655f" />

Here is a much shorter, simpler version that gets straight to the point and directly matches the screenshot you described:

TASK 9: Your Logic, Preloaded (Look-Up Tables)
For this task, I implemented a 2-input XOR function using a 4x1 Look-Up Table (LUT). Instead of computing the logic with standard gates, an LUT stores the answers from a truth table and uses the inputs to simply "look up" the correct output.

I built this using a 4x1 Multiplexer. A standard 2-input XOR gate outputs 0, 1, 1, and 0 for its four input combinations (00, 01, 10, 11). To program the LUT, I hardwired the four data pins of the multiplexer to those exact values. I then connected my two main inputs to the selector lines. As seen in the simulation, when the select inputs are set to 1 and 0, the multiplexer successfully retrieves the pre-stored 1, perfectly mimicking an XOR gate!


<img width="1037" height="541" alt="LUT" src="https://github.com/user-attachments/assets/37fa535f-ede4-4740-9b9e-0b29d1570ac4" />






