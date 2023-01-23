# Experiment--04-Implementation-of-combinational-logic-using-universal-gates
Implementation of combinational logic using universal-gates
 
## AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime


## Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

## Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

## Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

## Logic Diagram
## Procedure
## Program:
/*
Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.
Developed by: sentamilsaran S
RegisterNumber:  22008684
*/
Using NANAD gate
   module exp1(a,b,c,d,f);

   input a,b,c,d;
   
   output f;
   
   wire p,q,r;
   
   assign p=(~c & b & a);
   
   assign q=(~d & c & ~a);
   
   assign r=(c & ~b & a);
   
   assign f=(~(~p & ~q & ~r));
   
   endmodule
Using NOR gate

   module exp2(a,b,c,d,f);
   
   input a,b,c,d;
   
   output f;
   
   wire p,q,r;
   
   assign p=( c & ~b & a);
   
   assign q=( d & ~c & a);
   
   assign r=( c & ~b & a);
   
   assign f=(~(~( p | q | r)));
   
   endmodule realization

## Output:

## RTL
![image](https://user-images.githubusercontent.com/123304969/213965495-3bdea4c5-e422-496b-b10a-19ee0b61c3e7.png)
![image](https://user-images.githubusercontent.com/123304969/213965507-1244c065-cb38-4c8c-ba85-45eb0dd02ed3.png)

## Timing Diagram
![image](https://user-images.githubusercontent.com/123304969/213965609-2a3bece2-09da-4e6d-b567-6e2aa1d997ba.png)
![image](https://user-images.githubusercontent.com/123304969/213965634-ea48d1d8-de40-45eb-bb9e-4ada9014dc74.png)
## Truth table
![image](https://user-images.githubusercontent.com/123304969/213965693-45250699-3b54-4297-bda2-6fdf56feb53c.png)
![image](https://user-images.githubusercontent.com/123304969/213965709-203c6e12-9783-4346-9df1-af7adf7654dc.png)

## Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
