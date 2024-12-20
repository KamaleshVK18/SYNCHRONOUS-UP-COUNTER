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

/* write all the steps invloved */
```
1.Type the program required for the given experiment in quartus.
2.Make sure the program has been compiled successfully.
3.Run the RTL logic simulation.
4.Make the truth table.
5.Generate the output waveform.
```

**PROGRAM**

/* Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:V.KAMALESH VIJAYAKUMAR RegisterNumber:(24011704)
*/
```
module syn (
    output reg [3:0] out,
    input clk,
    input rst
);
    always @(posedge clk) begin
        if (rst)
            out <= 0;
        else
            out <= out + 1;
    end
endmodule
```


**RTL LOGIC UP COUNTER**
![image](https://github.com/user-attachments/assets/d84a6902-c4a6-4d0b-a901-31b7668b767a)


**TIMING DIAGRAM FOR IP COUNTER**
![image](https://github.com/user-attachments/assets/5e60bb85-48e7-4dd7-a49b-022b10aa214e)



**TRUTH TABLE**
![image](https://github.com/user-attachments/assets/fa8ba2d4-b6ed-4185-9e0d-2292e1cf5cfb)


**RESULTS**
The implementation of 4 bit synchronous up counter has been executed successfully and the functionality has been validated.

