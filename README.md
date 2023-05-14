### Experiment--02-Implementation-of-combinational-logic

Implementation of combinational logic gates
 
### AIM:

To implement the given logic function verify its operation in Quartus using Verilog programming.

F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D
 
F2=xy’z+x’y’z+w’xy+wx’y+wxy
 
### Equipments Required:

1. Hardware – PCs, Cyclone II , USB flasher
2. Software – Quartus prime

### Theory
 
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output.

### Using NAND gates

NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

### Using NOR GATES 

NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

### Logic Diagram

![image](https://user-images.githubusercontent.com/120443233/233106061-6c291b4b-d114-4ebf-8bd4-44415252a2bc.png)

### Procedure

1.Create a project with required entities.

2.Create a module along with respective file name.

3.Run the respective programs for the given boolean equations.

4.Run the module and get the respective RTL outputs.

5.Create university program(VWF) for getting timing diagram.

6.Give the respective inputs for timing diagram and obtain the results.

### Program:
/*
Program to implement the given logic function and to verify its operations in quartus using Verilog programming.

Developed by: M.A.VISHAL

RegisterNumber:212222230177
*/
```
### USING NAND gates:

module NAND(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R;
assign P=(~(~C & B & A));
assign Q=(~(~D & C & A));
assign R=(~(C & ~B & A));
assign F=~(P & Q & R);
endmodule
```
### Using NOR gates:
```
module NOR(A,B,C,D,F);
input A,B,C,D;
output F;
wire P,Q,R,S;
assign P = (C & ~B & A);
assign Q = (D & ~C & A);
assign R = (C & ~B & A);
assign S = (~(P | Q | R));
assign F = (~S);
endmodule
```
### RTL realization

### Output:

### RTL

### NAND combination

![image](https://user-images.githubusercontent.com/120443233/233108059-d754ccca-5155-498e-a964-b1893ad3ddc5.png)

NOR combination

![image](https://user-images.githubusercontent.com/120443233/233108238-1dbd1c4d-983a-4f66-9e21-710a39720a3d.png)

### Timing Diagram

### NAND combination

![image](https://user-images.githubusercontent.com/120443233/233108491-2df17d06-3f3e-44bf-a2dd-85e99dfa2021.png)

### NOR combination

![image](https://user-images.githubusercontent.com/120443233/233108614-7938ba5a-ff3b-4f9f-855a-cb88660feb35.png)

### Result:

Thus the given logic functions are implemented using  and their operations are verified using Verilog programming.

