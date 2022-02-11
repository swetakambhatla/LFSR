design of Linear feedback shift register

In a LFSR, D flip flops are used to form the shift register blocks and the output of few D flip flops is given to an EX-OR gate. Whose output id fed back to the first flipflop. This is called the feedback mechanism. Linear feedback shift registers make extremely good pseudorandom pattern generators. When the outputs of the flip-flops are loaded with a seed value (anything except all 0s, which would cause the LFSR to produce all 0 patterns) and when the clock signal is applied to the LFSR, it will generate a pseudorandom pattern of 1s and 0s. The only signal necessary to generate the test patterns is the clock. A n-bit LFSR produces the maximum number of PRPG patterns possible and has a pattern count equal to 2n – 1, where n is the number of register elements in the LFSR. The generation of patterns is done by transition. For example, for a 4-bit LFSR there will be 24-1=15 patterns generated and from 16th it will return to original state.

Ngspice
Ngspice is the open source spice simulator for electric and electronic circuits.
Ngspice implements various circuits elements, like resistors, capacitors, inductors (single or mutual), transmission lines and a number of semiconductor devices like diodes, bipolar transistors, MOSFETs, MESFETs, JFETs and HFETs.

Sky130 PDKs : Opensource PDK
The SkyWater Open Source PDK is a collaboration between Google and SkyWater Technology Foundry to provide a fully open source Process Design Kit and related resources, which can be used to create manufacturable designs at SkyWater's facility.

design of d flip flop

dff

output of dff
op1

ng spice netlist of d flip flop

C:\eSim-Workspace\d_ff1\d_ff1.cir
.lib "sky130_fd_pr/models/sky130.lib.spice" tt
xM1 vdd din Net-M1-Pad3 vdd sky130_fd_pr__pfet_01v8 w=1 l=0.5
xM2 vdd Net-M1-Pad3 vout vdd sky130_fd_pr__pfet_01v8 w=1 l=0.5
xM3 Net-M1-Pad3 clk Net-M3-Pad3 GND sky130_fd_pr__nfet_01v8 w=0.42 l=0.5
xM4 Net-M3-Pad3 din GND GND sky130_fd_pr__nfet_01v8 w=0.42 l=0.5
xM5 vout Net-M3-Pad3 GND GND sky130_fd_pr__nfet_01v8 w=0.42 l=0.5

Vdd vdd 0 5
Vd0 clk 0 pulse(0 5 0s 0s 0s 2us 10us)
Vd1 din 0 pulse(0 5 0s 0s 0s 3us 10us)
.tran 0.1us 80us
.control
run
plot V(vout) V(din)+8 V(clk)+16
.endc
.end

design of 3 BIT LFSR

image

esim design of LFSR

lfsr

Acknowledgement
Kunal Ghosh , Founder, VSD Corp. Pvt. Ltd
SFAL Team
Author
K SWETA, https://github.com/swetakambhatla/LFSR.