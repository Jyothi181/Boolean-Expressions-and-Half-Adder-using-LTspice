# Boolean-Expressions-using-LTspice

This repository explains the implementation of Boolean expressions in CMOS Logic using LT Spice Simulator. This shows the schematic of Boolean expressions and plot the output waveform to verify the functionality.

Table of Contents
Introduction Objectives Circuit Details Simulation Results

INTRODUCTION
A logic gate is a device that performs logical operations on one or more binary inputs and produces a single binary output. The primary way of building logic gates uses diodes or transistors acting as electronic switches. Today, most logic gates are made from MOSFETs (metal–oxide–semiconductor field-effect transistors). Logic circuits include such devices as multiplexers, registers, arithmetic logic units (ALUs), computer memory and microprocessors which may contain more than 100 million logic gates. Basic gates, also known as elementary or fundamental gates, include the AND, OR and NOT gates. These gates operates on binary signals (0s and 1s) and provide the basis for all digit computations. Other gates such as XOR, XNOR, NAND and NOR can be derived from basic gates.

Complementary metal–oxide–semiconductor (CMOS) is a type of MOSFET that uses complementary and symmetrical pairs of p-type and n-type MOSFETs for logic functions. Input is applied at the common gate of PMOS and NMOS transistors.Output is taken from the PMOS and NMOS drain. CMOS technology is used for constructing integrated circuit (IC) chips, including microprocessors, microcontrollers, memory chips and other digital logic circuits. Two important characteristics of CMOS devices are high noise immunity and low static power consumption.

PMOS: The PMOS transistor is a p-channel device. It conducts current when a negative voltage (logic low) is applied to its gate terminal with respect to the source terminal. In CMOS, PMOS acts as pull up network in which the source is connected to VDD. When logic low(0) is applied is CMOS, the PMOS transistor turns on and connects the VDD to output which makes the output to logic high(1).

NMOS: The NMOS transistor is an n-channel device. It conducts current when a positive voltage (logic high) is applied to its gate terminal with respect to the source terminal. In CMOS, MMOS acts as pull down network in which the source is connected to ground. When logic high(1) is applied is CMOS, the NMOS transistor turns on and connects the output to ground which makes the output to logic low(0).

OBJECTIVES
The main goal of this project are given below

To plot the schematics of logic gates, and circuits
To plot the output waveform
To verify the functionality
PROJECT STRUCTURE
Tool : LTspice Technology : C5N technology

LTspice Simulation Files: Files with .asc extension represents LTspice simulation files for each logic gate.
F1.asc : LTspice simulation file for F1 expression.
F2.asc : LTspice simulation file for F2 expression.
F3.asc : LTspice simulation file for F3 expression.

CIRCUIT DETAILS
The output of F1 expression produces. The logic symbol is shown below.









