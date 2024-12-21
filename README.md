### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**
```
1.Initialize the shift register to a known state (e.g., all zeros).

2.Input a bit serially into the shift register.

3.Shift the contents of the register one position to the right (or left).

4.Output the shifted bit from the last stage of the register.

5.Repeat steps 2-4 for each bit you want to input and shift. PROGRAM
```

/* write all the steps invloved */

**PROGRAM**
```
module e11(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 
```
Developed by: TAMILSELVI.I
RegisterNumber:24900261
Date:05/12/2024
```
*/

**RTL LOGIC UP COUNTER**

![Screenshot 2024-12-19 210115](https://github.com/user-attachments/assets/f4b26051-0fb7-4a47-9ad7-71754d94e45e)


**TIMING DIAGRAM FOR IP COUNTER**


![Screenshot 2024-12-19 210202](https://github.com/user-attachments/assets/bd5108da-633e-4eda-994b-b3242c9fb195)


**TRUTH TABLE**

![image](https://github.com/user-attachments/assets/e7dd23c0-5a08-49a0-b16c-b5823eb952f0)

**RESULTS**

 Hence a 4 bit synchronous up counter is implemented correctly and program code is successfully executed.


