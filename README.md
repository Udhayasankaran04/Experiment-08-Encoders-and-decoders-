# Experiment-07- Encoders-and-decoders 
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

1.create module encoder and decoder.

2.Get inputs and outputs for encoders and decoders.

3.perform or operation for encoder and and logic for decoders.

4.perform RTL LOGIC and get waveform.

### PROGRAM 
/*
Program for Endocers and Decoders  and verify its truth table in quartus using Verilog programming.
Developed by: SUDHARSAN RAM M
RegisterNumber:  212222110048
*/

```
ENCODER:
module encoder(a,b,c,d0,d1,d2,d3,d4,d5,d6,d7);
output a,b,c;
input d0,d1,d2,d3,d4,d5,d6,d7;
or(a,d4,d5,d6,d7);
or(b,d2,d3,d6,d7);
or(c,d1,d3,d5,d7);
endmodule


DECODER:
module decoder(d0,d1,d2,d3,d4,d5,d6,d7,a,b,c);
output d0,d1,d2,d3,d4,d5,d6,d7;
input a,b,c;
assign d0 = (~a&~b&~c);
assign d1 = (~a&~b&c);
assign d2 = (~a&b&~c);
assign d3 = (~a&b&c);
assign d4 = (a&~b&~c);
assign d5 = (a&~b&c);
assign d6 = (a&b&~c);
assign d7 = (a&b&c);
endmodule

```




### RTL LOGIC  

Encoder

![245388930-38853c0d-7042-48c7-bcca-0e96189a547a](https://github.com/Sudharsanram/Experiment-08-Encoders-and-decoders-/assets/119393980/0505e2bc-6aa2-4089-8fb1-5ce51951f26a)

Decoder

![245389094-5791712d-4bd6-40d8-a1d4-bd152078ce12](https://github.com/Sudharsanram/Experiment-08-Encoders-and-decoders-/assets/119393980/1311b817-7dd7-4db4-ab38-626a7c50826b)




### TIMING DIGRAMS  

Encoder

![245389255-4220560c-5266-4437-be66-3125c54fada7](https://github.com/Sudharsanram/Experiment-08-Encoders-and-decoders-/assets/119393980/c15a5f84-b485-4ac4-bef8-bf2dfe24a51e)

Decoder

![245389331-62130ea6-bbb8-4c60-8c2b-fa440ebe5cbe](https://github.com/Sudharsanram/Experiment-08-Encoders-and-decoders-/assets/119393980/407c8ad2-8534-4c7e-9a20-587c099696e0)





### TRUTH TABLE 

Encoder

![245389502-ccd3a5ea-a582-41c3-ae26-367af6183d62](https://github.com/Sudharsanram/Experiment-08-Encoders-and-decoders-/assets/119393980/19ff53e8-6da8-40c8-8aa0-91e21611531d)

Decoder

![245389543-a3ecb838-4e46-4043-ab49-2f16f2cc1b2a](https://github.com/Sudharsanram/Experiment-08-Encoders-and-decoders-/assets/119393980/5566e59d-7cdb-483f-a9b2-1acdef3d1522)


### RESULTS 

Thus the program to desing encoder and decoder is done.
