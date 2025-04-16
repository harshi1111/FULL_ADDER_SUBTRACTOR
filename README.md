## NAME : HARSHITHA V
## REGISTER NO : 212223230074
## EXP 4 : FULL ADDER AND SUBTRACTOR

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Truthtable**

![image](https://github.com/user-attachments/assets/1f46f2dd-3403-4fec-aa6c-665179ecbd7d)


**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

![image](https://github.com/user-attachments/assets/dd97f66f-9381-4738-9382-c77382df3361)


**Procedure**


1. Start the module  
   - The module is named ex4.  
   - It has 6 input signals: a, b, c, d, cin, and bin.  
   - It has 4 output signals: sum, carry, diff, and borrow.

2. Adder part  
   - sum is calculated using XOR of a, b, and cin  
     → sum = a ^ b ^ cin  
   - carry is calculated using AND and OR operations  
     → carry = (a & b) | (cin & (a ^ b))

3. Subtractor part  
   - diff is calculated using XOR of c, d, and bin  
     → diff = c ^ d ^ bin  
   - borrow is calculated using NOT, AND, and XOR operations  
     → borrow = (~c & d) | ((~c ^ d) & bin)

4. End the module  
   - The module ends with endmodule



**Program:**

```
module ex4 (a,b,c,d,cin,bin,diff,sum,carry,borrow);
input a,b,c,d,bin,cin;
output sum,carry,diff,borrow;
assign sum = a^b^cin;
assign carry = (a&b)|(cin & (a^b));
assign diff = c^d^bin;
assign borrow =(~c&d)|(((~c^d))& bin);
endmodule
```

**RTL Schematic**

![image](https://github.com/user-attachments/assets/35cf713c-0e89-4cdd-a361-aa5cc0e4176b)


**Output Timing Waveform**

![image](https://github.com/user-attachments/assets/b9c34fd8-2361-4825-a5de-70c1b1484e62)


**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



