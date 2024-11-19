# Boolean Expressions and Half Adder using-LTspice

This repository explains the implementation of Boolean expressions and Half Adder in CMOS Logic using LT Spice Simulator. This shows the schematics of Boolean expressions, Half Adder and plot the output waveform to verify the functionality.

# Table of Contents
- Introduction
- Objectives
- Project Structure
- Boolean Expressions Calculations
- Circuit Details
- Simulation Results

# Introduction
**Logic Gate:** A logic gate is a device that performs logical operations on one or more binary inputs and produces a single binary output. The primary way of building logic gates uses diodes or transistors acting as electronic switches. Today, most logic gates are made from MOSFETs (metal–oxide–semiconductor field-effect transistors). Logic circuits include such devices as multiplexers, registers, arithmetic logic units (ALUs), computer memory and microprocessors which may contain more than 100 million logic gates. Basic gates, also known as elementary or fundamental gates, include the AND, OR and NOT gates. These gates operates on binary signals (0s and 1s) and provide the basis for all digit computations. Other gates such as XOR, XNOR, NAND and NOR can be derived from basic gates.

**CMOS:** Complementary metal–oxide–semiconductor (CMOS) is a type of MOSFET that uses complementary and symmetrical pairs of p-type and n-type MOSFETs for logic functions. Input is applied at the common gate of PMOS and NMOS transistors.Output is taken from the PMOS and NMOS drain. CMOS technology is used for constructing integrated circuit (IC) chips, including microprocessors, microcontrollers, memory chips and other digital logic circuits. Two important characteristics of CMOS devices are high noise immunity and low static power consumption.

**PMOS:** The PMOS transistor is a p-channel device. It conducts current when a negative voltage (logic low) is applied to its gate terminal with respect to the source terminal. In CMOS, PMOS acts as pull up network in which the source is connected to VDD. When logic low(0) is applied is CMOS, the PMOS transistor turns on and connects the VDD to output which makes the output to logic high(1).

**NMOS:** The NMOS transistor is an n-channel device. It conducts current when a positive voltage (logic high) is applied to its gate terminal with respect to the source terminal. In CMOS, MMOS acts as pull down network in which the source is connected to ground. When logic high(1) is applied is CMOS, the NMOS transistor turns on and connects the output to ground which makes the output to logic low(0).

# Objectives
a) F1 = A XOR B  
b) F2 = (A+B) (C+D)  
c) F3 = (A.B) + (C.D)  
d) F4 = (PQ + R(S+T))’

- To draw the schematics of above mentioned boolean expressions and Half Adder.
- To plot the output waveform
- To verify the functionality


# Project Structure
- **Tool :** LTspice
- **Technology :** C5N technology

**LTspice Simulation Files:** Files with .asc extension represents LTspice simulation files for each logic gate.
- F1.asc : LTspice simulation file for F1 expression.
- F2.asc : LTspice simulation file for F2 expression.
- F3.asc : LTspice simulation file for F3 expression.
- F4.asc : LTspice simulation file for F4 expression.
- HALF_ADDER.asc : LTspice simulation file for Half adder.

# Boolean Expressions - Calculations

## F1
F1 = A’B +AB’  
F1 = (AB+A’B’)’  
| Boolean Expression | pmos | nmos|
| ------------------ | ---- | --- |
| AB | parallel | series|  
| A’B’ | parallel | series |
| (AB+A’B’)’ | series | parallel |

## F2
F2 = (A+B)(C+D)  
F2 = [((A+B)(C+D))’]’  
F2 = [(A+B)’+(C+D)’]’ 
| Boolean Expression | pmos | nmos|
| ------------------ | ---- | --- |
| (A+B)’ | series | parallel |  
| (C+D)’ | series | parallel |
| [(A+B)’+(C+D)’]’ | series | parallel |


## F3
F3 = (AB)+(CD)  
F3 = [((AB)+(CD))’]’  
F3 = [(AB)’(CD)’]’ 
| Boolean Expression | pmos | nmos|
| ------------------ | ---- | --- |
| (AB)' | parallel | series|  
| (CD)’ | parallel | series |
| [(AB)’(CD)’]’ |  parallel | series |

## F4
F4 = (PQ + R(S+T))’  
F4 = (PQ)’ [(R(S+T))’]  
F4 = (PQ)’ [R’+(S+T)’]
| Boolean Expression | pmos | nmos|
| ------------------ | ---- | --- |
| (S+T)' | series | parallel |  
| (PQ)’ | parallel | series |

## Half Adder
Sum = A’B+AB’  
Carry = AB   

Sum = (AB+A’B’)’ 
| Boolean Expression | pmos | nmos|
| ------------------ | ---- | --- |
| AB | parallel | series|  
| A’B’ | parallel | series |
| (AB+A’B’)’ | series | parallel |

Carry = ((AB)’)’ = (A’+B’)’
| Boolean Expression | pmos | nmos|
| ------------------ | ---- | --- |
| (A’+B’)’ | series | parallel |  

# LTspice Simulation

LTspice captures schematics of different circuits and shows the results of simulation by using waveform viewer. Circuit simulation analysis provides the transient, AC and DC analysis.

- Tool = LT spice Simulator
- Technology = C5N technology file
- VDD = 5v
- Spice Directive = `.include D:\NIELIT\ENGR3426\ENGR3426\engr3426.sub`
- Transient = `.tran 100u`
- PMOS -> Length = 0.6u, Width = 7.2u
- NMOS -> Length = 0.6u, Width = 3.6u
- PMOS = Pull Up Network (PUN)
- NMOS = Pull Down Network (PDN)

## Terms Description

- Inputs: The inputs are VA and VB. VA is applied to one of the PMOS and one of the NMOS. Likewise, VB is applied to one of the PMOS and one of the NMOS.
  
- Output: The output is based on the functionality of boolean expressions.

- VDD is voltage source
  
- PULSE(0 5 1n 1n 5u 10u) is a syntax used to define a pulse waveform for respective voltage sources

- Initial Value (Vintial): 0[V] This is the voltage level of the source before the pulse begins.

- Pulse Value (Von): 5[V] This is the voltage level during the ON period of the pulse.

- Delay Time (Tdelay): 0[s] This is the delay time from input voltage to output voltage. In this case, there is no delay.

- Rise Time (Trise): 1n[s] This is the time taken for the pulse to change from the Initial Value to the Pulse Value.

- Fall Time (Tfall): 1n[s] This is the time taken for the pulse to change from the Pulse Value back to the Initial Value.

- On Time (Ton): 5u This is the time for which the pulse on for some period of time

- Time period (Tperiod): 10us This is the total time for one complete cycle of the pulse waveform.

- Number of Cycles (Ncycles): 10 This specifies how many cycles of the pulse waveform should be generated.

- Spice Directive: This contains text directly passes to the netlist which is placed on the schematic. The text may be single line or block or lines.

- Transient Analysis: This analyzes the changes in voltage and current over time when an input signal is applied. To apply tansient analysis .tran is used as a keyword.

So, with the given inputs, the voltage source will start at initial value, then immediately rise to pulse value. It will remain at pulse value for on time, then drop back down to initial vlaue. The total period for one complete cycle of this waveform will repeat 10 times.

# Schematics

## Schematic of F1

- VA and VB are input voltages
- F1 is output
- VA = `PULSE(0 5 0 1n 1n 5u 10u)`
- VB = `PULSE(0 5 0 1n 1n 10u 20u)`

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture24.png)

***Figure 1: LTspice Schematic of F1 expression***

## Schematic of F2

- VA, VB, VC and VD are input voltages
- F2 is output
- VA = `PULSE(0 5 0 1n 1n 5u 10u)`
- VB = `PULSE(0 5 0 1n 1n 10u 15u)`
- VC = `PULSE(0 5 0 1n 1n 15u 20u)`
- VD = `PULSE(0 5 0 1n 1n 20u 25u)`
   
![image](https://github.com/Jyothi181/Pictures/blob/main/Picture25.png)

***Figure 2: LTspice Schematic of F2 expression***

## Schematic of F3

- VA, VB, VC and VD are input voltages
- F3 is output
- VA = `PULSE(0 5 0 1n 1n 5u 10u)`
- VB = `PULSE(0 5 0 1n 1n 10u 15u)`
- VC = `PULSE(0 5 0 1n 1n 15u 20u)`
- VD = `PULSE(0 5 0 1n 1n 20u 25u)`
- 
![image](https://github.com/Jyothi181/Pictures/blob/main/Picture26.png)

***Figure 3: LTspice Schematic of F3 expression***

## Schematic of F4

- VP, VQ, VR, VS and VT are input voltages
- F4 is output
- VP = `PULSE(0 5 0 1n 1n 5u 10u)`
- VQ = `PULSE(0 5 0 1n 1n 10u 15u)`
- VR = `PULSE(0 5 0 1n 1n 15u 20u)`
- VS = `PULSE(0 5 0 1n 1n 20u 25u)`
- VT = `PULSE(0 5 0 1n 1n 25u 30u)`
   
![image](https://github.com/Jyothi181/Pictures/blob/main/Picture27.png)

***Figure 4: LTspice Schematic oF F4 expression***
  
![image](https://github.com/Jyothi181/Pictures/blob/main/Picture28.png)     ![image](https://github.com/Jyothi181/Pictures/blob/main/Picture29.png)

## Schematic of Half Adder

- VA and VB are input voltages
- F1 is output
- VA = `PULSE(0 5 0 1n 1n 5u 10u)`
- VB = `PULSE(0 5 0 1n 1n 10u 20u)`
  
![image](https://github.com/Jyothi181/Pictures/blob/main/Picture30.png)

***Figure 5: LTspice Schematic of Half Adder***

# Simulation Results

## How to simulate

- Once the schematic is done, click on `Run/Pause(Alt+R)` to run the schematic.
- Select the `Add Plot Pane Above` option by left click on the waveform viewer window. Add 3 panes for 2 inputs and 1 output.
- To plot the graphs, click on the specific pane and each input and output nodes.

## Results
The pulse rises from initial value to pulse value. Depending on the pulse width and period settings, the pulse will repeat at regular intervals. The generated output is based on the applied inputs and the logical functionality. The graphs VA - V(n002), VB - V(n003) and Vout - V(vout) represent the inputs and output respectively with different colours. The simulation results verifies the functionality of circuits.

The graphs VA - V(a), VB - V(b) and Vout - V(f1) represent the inputs and output respectively

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture31.png)

***Figure 6: Simulated waveform of F1 expression***

The graphs VA - V(n002), VB - V(n005), VC  - V(n008), VD - V(n009) and Vout - V(f2) represent the inputs and output respectively
 
![image](https://github.com/Jyothi181/Pictures/blob/main/Picture32.png)

***Figure 7: Simulated waveform of F2 expression***

The graphs VA - V(n002), VB - V(n003), VC  - V(n008), VD - V(n009) and Vout - V(f3) represent the inputs and output respectively
 
![image](https://github.com/Jyothi181/Pictures/blob/main/Picture33.png)

***Figure 8: Simulated waveform of F3 expression***

The graphs VP - V(p), VQ - V(q), VR  - V(r), VS - V(s) and VT - V(t) represent the inputs and output respectively

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture34.png)

***Figure 9: Simulated waveform of F4 expression***

The graphs  VA - V(a), VB - V(b), Vout - V(sum), and Vout - V(carry) represent the inputs and output respectively

![image](https://github.com/Jyothi181/Pictures/blob/main/Picture35.png)

***Figure 10: Simulated waveform of Half Adder***



