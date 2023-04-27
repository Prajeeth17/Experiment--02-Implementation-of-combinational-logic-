# Experiment--02-Implementation-of-combinational-logic
Implementation of combinational logic gates
 
## AIM:
To implement the given logic function verify its operation in Quartus using Verilog programming.

1. F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D

2. F2=xy’z+x’y’z+w’xy+wx’y+wxy

## Equipments Required:
Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime


## Theory:

Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

1.AND gate The AND gate is an electronic circuit that gives a high output (1) only if all its inputs are high. A dot (.) is used to show the AND operation i.e. A.B or can be written as AB Y= A.B

2.OR gate The OR gate is an electronic circuit that gives a high output (1) if one or more of its inputs are high. A plus (+) is used to show the OR operation. Y= A+B

## Procedure:
1. Use module projname(input,output) to start the Verilog programmming.
2. Assign inputs and outputs using the word input and output respectively.
3. Use defined keywords like wire,assign and required logic gates to represent the boolean expression.
4. Use each output to represent one for F1 and the other for F2.
5. End the verilog program using keyword endmodule.

## Program:
```c
/*
Program to implement the given logic function and to verify its operations in quartus using Verilog programming.
Developed by: Prajeeth K T
RegisterNumber: 212222110034
*/

// F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D

module imp(A,B,C,D,F1);
input A,B,C,D;
output F1;
wire p,q,r,s,t;
assign p = (~A & ~B & ~C & ~D);
assign q = (A & ~C & ~D);
assign r = (~B & C & ~D);
assign s = (~A & B & C & D);
assign t = (B & ~C & D);
assign F1 = p | q | r | s | t;
endmodule

// F2=xy’z+x’y’z+w’xy+wx’y+wxy

module imp(w,x,y,z,F2);
input w,x,y,z;
output F2;
wire p,q,r,s,t;
assign p= (x & ~y & z);
assign q= (~x & ~y & z);
assign r= (~w & x & y);
assign s= (w & ~x & y);
assign t= (w & x & y);
assign F2= p | q | r | s | t;
endmodule

```


## Output:

### Logical diagram:
![logic](/outputs/ld.jpg)

### RTL realization:

For F1:
![f1](/outputs/rtlf1.jpg)

For F2:
![f2](/outputs/rtlf2.jpg)

### Timing Diagram:

For F1:
![f1](/outputs/tdf1.png)

For F2:
![f2](/outputs/tdf2.png)

## Result:
Thus the given logic functions are implemented using  and their operations are verified using Verilog programming.