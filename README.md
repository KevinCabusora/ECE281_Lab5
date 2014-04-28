ECE281_Lab5
===========

PRISM on Nexys Board

### Description of Program

First, the program loads a value from the operand address into the accumulator, which is 8.

Next, the value of the operand is added to the accumulator, which is 1.

The next command outputs the value to output port 3.

The next command, JN, reads the most significant (leftmost) bit.  If it is negative, it loops back up to add 1 to the accumulator again.

Finally, a jump is at the end which begins on the same line, resulting in an infinite loop that completes the program.

### Waveform

![Waveform with instructions](https://github.com/KevinCabusora/ECE281_Lab5/blob/master/Waveform_w_Instructions.PNG?raw=true "Image")

### Questions

1.	When the controller’s current state is “FETCH,” what is the status of the following control lines:

a.	PCLd = 1

b.	IRLd = 1

c.	ACCLd 0

2.	The current state is Decode LoAddr and the IR contains “OUT.”  What are the control signals are asserted, and what will the next state be?

Control Signals asserted include MARLoLD, MemSel_L, and PCLd.

The next state will be Direct I/O Execute.


3.	What are the three status signals sent from the PRISM datapath to the PRISM controller?

The three status signals include the current value of IR, A < 0 and A = 0.


4.	Why is it important that ACCLd signal be active during the execute state for the ADDI instruction?

ADDI dictates that the accumulator is loaded with the value in the operand, and the accumulator can only be written when ACCLd is active.


5.	What changes are necessary to the PRISM datapath to add another instruction (SUBI, which would subtract an immediate value from the accumulator) to the instruction set?

One such change would be a multiplexer that would include one more instruction, with a total of 17 instructions.  OpSel would also have to be bigger than 3 bits in order to accommodate 8 choices, so a 4th bit is needed.
