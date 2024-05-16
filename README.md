EXP-4 SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC CIRCUITS

Date: 02.4.24,16.4.24


AIM: 
 To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN using Xilinx ISE.

APPARATUS REQUIRED:

Xilinx 14.7
Spartan6 FPGA

PROCEDURE:
```
STEP:1  Start  the Xilinx navigator, Select and Name the New project.
STEP:2  Select the device family, device, package and speed.       
STEP:3  Select new source in the New Project and select Verilog Module as the Source type.                       
STEP:4  Type the File Name and Click Next and then finish button. Type the code and save it.
STEP:5  Select the Behavioral Simulation in the Source Window and click the check syntax.                       
STEP:6  Click the simulation to simulate the program and  give the inputs and verify the outputs as per the truth table.               
STEP:7  Select the Implementation in the Sources Window and select the required file in the Processes Window.
STEP:8  Select Check Syntax from the Synthesize  XST Process. Double Click in the  FloorplanArea/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. 
STEP:9  In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu.
STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here.
STEP:11  On the board, by giving required input, the LEDs starts to glow light, indicating the output.
```


**LOGIC DIAGRAM**

SR FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/77fb7f38-5649-4778-a987-8468df9ea3c3)

VERILOG CODE:

```
module srflipflop(clk,res,s,r,q);
input clk,res,s,r;
output reg q;
always@(posedge clk)
begin
if(res)
q<=1'b0;
else begin
case({s,r})
2'b00:q<=q;
2'b01:q<=1'b0;
2'b10:q<=1'b1;


2'b11:q<=1'bx;
default:q<=1'bx;
endcase
end
end
endmodule
```

OUTPUT:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/161426740/219694fa-d6d5-4165-b8b3-0007e63196ef)



JK FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/1510e030-4ddc-42b1-88ce-d00f6f0dc7e6)

VERILOG CODE:

```
module jk(clk,res,j,k,q);
input clk,res,j,k;
output reg q;
always@(posedge clk)
begin
if(res)
q<=1'b0;
else begin
case({j,k})
2'b00:q<=q;
2'b01:q<=1'b0;
2'b10:q<=1'b1;
2'b11:q<=~q;
default:q<=~q;
endcase
end
end
endmodule
```

OUTPUT:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/161426740/4f1fa6c8-b41f-4348-ac03-c29b06cbf6d5)


T FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/7a020379-efb1-4104-85ee-439d660baa08)

VERILOG CODE:

```
module tflipflop(clk,res,q,t);
input clk,res,t;
output reg q;
always@(posedge clk)
begin
if(res)
q<=1'b0;
else
begin
if(res)
q<=0;
else if(t)
q<=~q;
else
q<=q;

end
end
endmodule
```

OUTPUT:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/161426740/dce37063-0516-415e-8904-21a2a8de1835)



D FLIPFLOP

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/dda843c5-f0a0-4b51-93a2-eaa4b7fa8aa0)

VERILOG CODE:

```
module dflipflop(c,r,d,q);
input c,r,d;
output reg q;


always @(posedge c)
begin
if(r)
q<= 1'b0 ;
else
q<=d;
end
endmodule
```

OUTPUT:


![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/161426740/a358faf6-6c60-4a4b-ad9c-a445b6b5b83b)




COUNTER

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/6987778/a1fc5f68-aafb-49a1-93d2-779529f525fa)

VERILOG CODE:

```
module upcounter(clk,rest,count);
input clk,rest;
output [3:0]count;
reg[3:0]count;
always@(posedge clk)
begin
if(rest)
count<=4'b0;
else
count<=count+1;
end
endmodule
```

OUTPUT:

![image](https://github.com/navaneethans/VLSI-LAB-EXP-4/assets/161426740/68faa57b-0967-4e06-9567-6d6ba46b0c54)



  



RESULT:

     Thus ,the given SR flip flop,Jk flip flop, D flip flop,T flip flop and Counter are simulated and synthesis are executed successfully.


