# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
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



Write the detailed procedure here 


## Program:
```
module halfsubtractor(a,b,difference,borrow);
inputs a,b;
outputs difference,borrow;
wire x;
xor(difference,a,b);
not(x,a);
and(borrow,x,b);
endmodule
```
```
module fullsubtractor(A,B,C,Difference,Borrow);
input A,B,C;
output Difference,Borrow;
wire p;
assign Difference=((A^B)^C);
not(p,A);
assign Borrow=((p&B)|(p&C)|(B&C));
endmodule
```

/*
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: Yuvarani T
RegisterNumber:22009033  
*/

## Truthtable

HALF SUBTRACTOR
![half sub truthtable](https://user-images.githubusercontent.com/121418522/213157495-55fe7372-034a-4deb-a57a-c7808e35f670.png)

FULL SUBTRACTOR
![full sub truthtable](https://user-images.githubusercontent.com/121418522/213157894-a8d50f39-7ebd-4939-a458-b86dda3fd8c5.png)

##  RTL realization

HALF SUBTRACTOR
![Screenshot (11)](https://user-images.githubusercontent.com/121418522/213158874-e8b2d587-983b-4ce9-94a8-d02796244242.png)

FULL SUBTRACTOR
![FULL ADD RTL](https://user-images.githubusercontent.com/121418522/213158970-1ed9870b-7017-43e0-9ea8-bbc29143b500.png)

## Timing diagram 

HALF SUBTRACTOR
![HALF SUB TIMING](https://user-images.githubusercontent.com/121418522/213159175-215553f5-6987-43ea-9998-7ecb416df729.png)

FULL SUBTRACTOR
![FULL SUB TIMING](https://user-images.githubusercontent.com/121418522/213159281-b50738f9-2fd3-4928-b64d-5509417aba3a.png)

## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
