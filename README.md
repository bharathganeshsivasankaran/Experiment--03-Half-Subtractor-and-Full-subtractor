# Experiment--04-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
Hardware – PCs,Cyclone II , USB flasher Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.
## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
 1.Use module projname(input,output) to start the Verilog programmming.
 2.Assign inputs and outputs using the word input and output respectively.
 3.Use defined keywords like wire,assign and required logic gates to represent the boolean expression.
 4.Use each output to represnt onre for differnce and the other for borrow.
 5.End the verilog program using keyword endmodule.
## Program:
```
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: BHARATHGANESH S
RegisterNumber:  212222230022
```
### HALF SUBTRACTOR
```
module HalfSubtractor(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule
```

### FULL SUBTRACTOR
```
module FullSubtractor(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule
```
##  RTL realization:

### HALF SUBTRACTOR
![266500479-5cf3d663-21e0-49b7-aee3-2e40041d64d2](https://github.com/bharathganeshsivasankaran/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119478098/27ca0bf2-dbdc-44bc-b2de-b47243ce9370)


### FULL SUBTRACTOR
![266500432-c6afcd88-9848-41b4-939b-229a3ecfec0f](https://github.com/bharathganeshsivasankaran/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119478098/ba0e4cf3-31b9-45d6-ab8c-11d437af9611)

## Truthtable
### HALF SUBTRACTOR
![266500581-1a822ddb-e2e4-46cf-be6d-1397905586f8](https://github.com/bharathganeshsivasankaran/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119478098/96fc216d-79f8-48a1-ae63-de090a1bfcbd)
### FULL SUBTRACTOR
![266500561-b61b4b97-06af-43f4-9adc-606763629835](https://github.com/bharathganeshsivasankaran/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119478098/0f1e7925-db97-49ef-add4-0e73823daf25)
## Timing diagram 
### HALF SUBTRACTOR
![266500538-7df7020f-4814-4ec2-9ca6-50ef18e7da16](https://github.com/bharathganeshsivasankaran/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119478098/38f18c81-b8ba-4b42-8ecf-3dff7bd6b810)


### FULL SUBTRACTOR
![266500527-6338d049-6ef3-41be-9d17-ddaebfa08d85](https://github.com/bharathganeshsivasankaran/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/119478098/b17b605a-1026-41a0-b861-78d90d7a35d2)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
