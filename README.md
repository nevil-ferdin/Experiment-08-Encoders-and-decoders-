# Experiment-08- Encoders-and-decoders 
### AIM: To implement 8 to 3 Encoder and  3to8 Decoder using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## Encoders
Binary code of N digits can be used to store 2N distinct elements of coded information. This is what encoders and decoders are used for. Encoders convert 2N lines of input into a code of N bits and Decoders decode the N bits into 2N lines.

1. Encoders –
An encoder is a combinational circuit that converts binary information in the form of a 2N input lines into N output lines, which represent N bit code for the input. For simple encoders, it is assumed that only one input line is active at a time.

As an example, let’s consider Octal to Binary encoder. As shown in the following figure, an octal-to-binary encoder takes 8 input lines and generates 3 output lines.

![image](https://user-images.githubusercontent.com/36288975/171543588-bc0746df-a173-4b35-989e-5fb7d385fe8a.png)
## Figure -01 3 to 8 Encoder 


Implementation –

X = D4 + D5 + D6 + D7
Y = D2 +D3 + D6 + D7
Z = D1 + D3 + D5 + D7 
Hence, the encoder can be realised with OR gates as follows:


![image](https://user-images.githubusercontent.com/36288975/171543740-68403b82-aa93-4c98-9343-f32b14885a2e.png)
## Figure -02 3 to 8 Encoder implenentation 

 ### Decoders 
A decoder does the opposite job of an encoder. It is a combinational circuit that converts n lines of input into 2n lines of output.

Let’s take an example of 3-to-8 line decoder.
Implementation –
D0 is high when X = 0, Y = 0 and Z = 0. Hence,

D0 = X’ Y’ Z’ 
Similarly,

D1 = X’ Y’ Z
D2 = X’ Y Z’
D3 = X’ Y Z
D4 = X Y’ Z’
D5 = X Y’ Z
D6 = X Y Z’
D7 = X Y Z 


![image](https://user-images.githubusercontent.com/36288975/171543978-ee2d0671-2846-40a1-8705-507fd6287a49.png)
## Figure -03 8 to 3 Decoder 



![image](https://user-images.githubusercontent.com/36288975/171543866-5a6eace6-8683-49d7-9c4f-a7cb30ec3035.png)
## Figure -04 8 to 3 Decoder implementation 

### Procedure

#### Step 1:
Open Quartus II and select new project and choose the file location.

#### Step 2:
Module Declaration. Module should have the file name.
#### Step 3:
Input-Output Delecaration.

#### Step 4:
Use assign to define the functionality of logic circuits.

#### Step 5:
At the end give endmodule.

#### Step 6:
Run the program and choose RTL viewer to get RTL realization.

### PROGRAM 
```verilog
FOR ENCODER

module encoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule
```
```verilog
FOR DECODER
module decoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
output d0,d1,d2,d3,d4,d5,d6,d7;
input a,b,c;
assign d0=(~a & ~b & ~c);
assign d1=(~a & ~b & c);
assign d2=(~a & b & ~c);
assign d3=(~a & b & c);
assign d4=(a & ~b & ~c);
assign d5=(a & ~b & c);
assign d6=(a & b & ~c);
assign d7=(a & b & c);
endmodule

```
```
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: P.Nevil Joe Ferdin
RegisterNumber:  212222050041
```






### RTL LOGIC  
#### FOR ENCODER
![encoderrtl](https://github.com/nevil-ferdin/Experiment-08-Encoders-and-decoders-/assets/115524975/3dd0b5c7-1822-4d46-aa6e-5e9d2ea068e8)


#### FOR DECODER




![decoderrtl](https://github.com/nevil-ferdin/Experiment-08-Encoders-and-decoders-/assets/115524975/ae46d50a-68a6-4336-bfd7-07628809c942)




### TIMING DIGRAMS  

#### FOR ENCODER
![enodertd](https://github.com/nevil-ferdin/Experiment-08-Encoders-and-decoders-/assets/115524975/6a990601-b659-44ba-b34b-49e14478e7c1)

#### FOR DECODER

![decoder td](https://github.com/nevil-ferdin/Experiment-08-Encoders-and-decoders-/assets/115524975/598063bf-3142-47db-9371-42b3673ea6e3)

### TRUTH TABLE 

#### FOR ENCODER
![encoder tt](https://github.com/nevil-ferdin/Experiment-08-Encoders-and-decoders-/assets/115524975/e85e175f-7965-4ec6-85f9-27eb6c998a52)

#### FOR DECODER
![decoder tt](https://github.com/nevil-ferdin/Experiment-08-Encoders-and-decoders-/assets/115524975/f4109b96-5149-43ae-a7e9-ac4a1adc524f)



### RESULTS
+ 8 to 3 Encoder and 3 to 8 Decoder has been implemented by using verilog and its outputs are validated.
