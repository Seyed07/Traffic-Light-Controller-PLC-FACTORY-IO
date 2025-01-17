# Traffic Light Controller PLC and Factory IO
The system has been developed and tested using **Factory IO software** for simulation and **Siemens Step 7’s Simatic Manager** with an **S300 PLC** for programming and control.

This project implements a Traffic Light Control System for a four-way intersection using a PLC (Programmable Logic Controller). The control system operates two traffic lights with a predefined sequence of operations:

- **Stage 1 (20 seconds):** Traffic Light 1 is Green, and Traffic Light 2 is Red.
- **Stage 2 (7 seconds):** Both Traffic Lights 1 and 2 turn Yellow.
- **Stage 3 (20 seconds):** Traffic Light 1 is Red, and Traffic Light 2 is Green.

## Traffic Light Control Logic and Timer Sequence

The system begins when the Start button is pressed, turning on the Start light and turning off the Stop light. The Start button also sets the memory bit to 1, activating the timer. The timer then starts counting, and its output remains at 1 for 20 seconds, holding the output high for the specified duration. This is achieved using a PEXT timer (extended timer), which, when activated, holds the output high for a specified period (TV seconds) and then sets the output to 0 after the set time.

Once the timer output is high, Traffic Light 1 turns green, and Traffic Light 2 turns red. After 20 seconds, the timer output goes to 0, and both traffic lights turn off. A falling edge (N) is created, signaling the start of the next stage.

In the second stage, the same logic applies, but this time both Traffic Lights turn yellow for 7 seconds. After 7 seconds, the timer output goes to 0 again, creating another falling edge and signaling the start of the third stage.

During the third stage, the timer activates once more, causing Traffic Light 1 to turn red and Traffic Light 2 to turn green for 20 seconds. After 20 seconds, the system resets using a normally closed (NC) contact, and the cycle repeats with the timers reset for the next iteration.

This structure ensures the traffic light sequence is properly managed, with precise control over each stage using memory and timers