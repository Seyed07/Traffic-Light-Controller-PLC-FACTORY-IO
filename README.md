# Traffic Light Controller PLC and Factory IO
The system has been developed and tested using **Factory IO software** for simulation and **Siemens Step 7’s Simatic Manager** with an **S300 PLC** for programming and control.

This project implements a Traffic Light Control System for a four-way intersection using a PLC (Programmable Logic Controller). The control system operates two traffic lights with a predefined sequence of operations:

- **Stage 1 (20 seconds):** Traffic Light 1 is Green, and Traffic Light 2 is Red.
- **Stage 2 (7 seconds):** Both Traffic Lights 1 and 2 turn Yellow.
- **Stage 3 (20 seconds):** Traffic Light 1 is Red, and Traffic Light 2 is Green.

The cycle repeats after the third stage. The system is activated by a Start button, triggering the sequential activation of the traffic lights. This project simulates the timing and sequencing needed to safely control traffic at an intersection, ensuring a clear flow for each direction at the appropriate times.

