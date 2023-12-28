# NAME NITHISH S
# REFERENCE NUMBER
# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 
# PROCEDURE
1. TYPE THE PROGRAM IN QUARTUS SOFTWARE.
2. COMPILE AND RUN THE PROGRAM.
3. GENERATE THE RTL SCHEMATIC AND SAVE THE LOGIC DIAGRAM.
4. CREATE NODES FOR  INPUTS AND OUTPUTS TO GENERATE THE TIMING DIAGRAM.
5. FOR DIFFERENT INPUT COMBINATIONS,GENERATE THE TIMING DIAGRAM
   
## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.
The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.
The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.
Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.



 
 

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

 # PROGRAM
```module up_counter(clk,q1,q2,q3);
input clk;
output reg q1,q2,q3;
always@(posedge clk)
begin
q3=(q1&q2)^q3;
q2=q1^q2;
q1=1^q1;
end 
endmodule
 ```
# RTL LOGIC FOR UP COUNTER

 ![293053998-42e688c9-0f09-4855-aa94-999ef57fbd7c](https://github.com/Nithish23013509/Exp-7-Synchornous-counters-/assets/149038138/270fc209-b0d2-402c-a45b-812019c64735)
# TRUTH TABLE

![293053425-61101a6c-3bc6-4673-8f28-a6cc96261e20](https://github.com/Nithish23013509/Exp-7-Synchornous-counters-/assets/149038138/5f76ff22-b25d-4eaa-a13a-b2941bd14163)

#TIMING DIAGRAM FOR UP COUNTER

![293053302-503e5497-1348-4cfe-8cb9-f85522c71464](https://github.com/Nithish23013509/Exp-7-Synchornous-counters-/assets/149038138/5914f8de-70d8-4831-b092-deb933eec141)



## DOWN COUNTER 

As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)



### PROGRAM 
```
module COUNTER(clk,q1,q2,q3);
input clk;
output reg q1,q2,q3;
always@(posedge clk)
begin
q3=((~q2)&(~q1))^q3;
q2=(~q1)^q2;
q1=1^q1;
end
endmodule
```




### RTL LOGIC  DOWN COUNTER  



![293052592-86302d1a-9941-44f5-b0c5-b4a4d197801c](https://github.com/Nithish23013509/Exp-7-Synchornous-counters-/assets/149038138/9efa1c37-00f0-4a04-80f1-5d4fdff715af)



### TRUTH TABLE 



![293052864-f1f16bd2-e699-431f-b573-37a9d7058932](https://github.com/Nithish23013509/Exp-7-Synchornous-counters-/assets/149038138/08d0e05c-c01e-4b9e-b065-633593dbf368)


# TIMING DIAGRAM FOR DOWN COUNTER

![293052816-2eebdbcf-f101-471e-a1b2-24a7d524a12f](https://github.com/Nithish23013509/Exp-7-Synchornous-counters-/assets/149038138/9f48bd2f-d6be-43c0-969e-c2c69a6e365e)


### RESULTS
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.

