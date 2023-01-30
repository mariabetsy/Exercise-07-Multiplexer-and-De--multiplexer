# Exercise-07-Multiplexer-and-De-multiplexer
### AIM: To implement 4 X1 multiplexer and 1X4 de multiplexer using verilog and validate its outputs
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 

## What are Multiplexer and Demultiplexer?
In-network transmission, both the multiplexer and demultiplexer are combinational circuits. A multiplexer selects an input from several inputs then it is transmitted in the form of a single line. An alternative name of the multiplexer is MUX or data selector. A demultiplexer uses one input signal and generates many. So it is known as Demux or data distributor.

## What is a Multiplexer?
The multiplexer is a device that has multiple inputs and single line output. The select lines determine which input is connected to the output, and also increase the amount of data that can be sent over a network within a certain time. It is also called a data selector.

The single-pole multi-position switch is a simple example of a non-electronic circuit of the multiplexer, and it is widely used in many electronic circuits. The multiplexer is used to perform high-speed switching and is constructed by electronic components.

![image](https://user-images.githubusercontent.com/36288975/170912485-73c395c7-23c0-4e78-a53d-a2f0d07d9662.png)
          Figure-01 multiplexer block diagram 

Multiplexers are capable of handling both analog and digital applications. In analog applications, multiplexers are made up of relays and transistor switches, whereas in digital applications, the multiplexers are built from standard logic gates. When the multiplexer is used for digital applications, it is called a digital multiplexer.

4-to-1 Multiplexer
The 4X1 multiplexer comprises 4-input bits, 1- output bit, and 2- control bits. The four input bits are namely 0, D1, D2, and D3, respectively; only one of the input bits is transmitted to the output. The o/p ‘q’ depends on the value of control input AB. The control bit AB decides which of the i/p data bit should transmit the output. The following figure shows the 4X1 multiplexer circuit diagram using AND gates. For example, when the control bits AB =00, then the higher AND gates are allowed while remaining AND gates are restricted. Thus, data input D0 is transmitted to the output ‘q”
![image](https://user-images.githubusercontent.com/36288975/170912568-3598c60a-5035-41f3-b0c4-ccedba13aca5.png)


Figure2 4X1 multiplexer 
If the control input is changed to 11, then all gates are restricted except the bottom AND gate. In this case, D3 is transmitted to the output, and q=D0. If the control input is changed to AB =11, all gates are disabled except the bottom AND gate. In this case, D3 is transmitted to the output, and q = D3. The best example of a 4X1 multiplexer is IC 74153. In this IC, the o/p is the same as the i/p. Another example of a 4X1 multiplexer is IC 45352. In this IC, the o/p is the compliment of the i/p


## What is Demultiplexer?
De-multiplexer is also a device with one input and multiple output lines. It is used to send a signal to one of the many devices. The main difference between a multiplexer and a de-multiplexer is that a multiplexer takes two or more signals and encodes them on a wire, whereas a de-multiplexer does reverse to what the multiplexer does.
![image](https://user-images.githubusercontent.com/36288975/170912606-a30e4b74-1726-4430-b245-2c3c3d9c232d.png)
Figure 3 De-multiplexer 
1-4 Demultiplexer
The 1-to-4 demultiplexer comprises 1- input bit, 4-output bits, and control bits. The 1X4 demultiplexer circuit diagram is shown below.![image](https://user-images.githubusercontent.com/36288975/170912683-00fb746a-1d45-4023-91d1-3a70b841073c.png)

![image](https://user-images.githubusercontent.com/36288975/170912741-7cbd52af-7e0d-4be3-b5c6-6fb9c4eca7c9.png)

Figure4 1X4 De-multiplexer 
The i/p bit is considered as Data D. This data bit is transmitted to the data bit of the o/p lines, which depends on the AB value and the control i/p.

When the control i/p AB = 01, the upper second AND gate is permitted while the remaining AND gates are restricted. Thus, only data bit D is transmitted to the output, and Y1 = Data.

If the data bit D is low, the output Y1 is low. IF data bit D is high, the output Y1 is high. The value of the output Y1 depends upon the value of data bit D, the remaining outputs are in a low state.

If the control input changes to AB = 10, then all the gates are restricted except the third AND gate from the top. Then, data bit D is transmitted only to the output Y2; and, Y2 = Data. . The best example of 1X4 demultiplexer is IC 74155.

 
 
### Procedure
/* write all the steps involved
Start the module using module projname(). Declare the inputs and outputs along with the select lines according to the multiplexer and demultiplexer. Use wire to assign intermediate outputs. Use and,or and not gates to get the desired output. End the module. Generate RTL realization and timing diagrams


### PROGRAM 
/*
Program for flipflops  and verify its truth table in quartus using Verilog programming.
Developed by:Maria Betsy G 
RegisterNumber:22008543  
*/
MULTIPLEXER

module mux(I0,I1,I2,I3,S0,S1,Y); input I0,I1,I2,I3,S0,S1; output Y; wire S0C,S1C; not(S0C,S0); not(S1C,S1); wire P,Q,R,S; and(P,S0C,S1C,I0); and(Q,S0C,S1,I1); and(R,S0,S1C,I2); and(S,S0,S1,I3); or(Y,P,Q,R,S); endmodule

DEMULTIPLEXER

module demux(I,S0,S1,Y0,Y1,Y2,Y3); input I,S0,S1; output Y0,Y1,Y2,Y3; wire S0C,S1C; not(S0C,S0); not(S1C,S1); and(Y0,I,S0C,S1C); and(Y1,I,S0C,S1); and(Y2,I,S0,S1C); and(Y3,I,S0,S1); endmodule







### RTL LOGIC  

MULTIPLEXER
![image](https://user-images.githubusercontent.com/122356434/215397090-4e410b44-d451-4efb-ad31-7abc15daf4e5.png)


DEMULTIPLEXER
![image](https://user-images.githubusercontent.com/122356434/215397113-6c5294d6-fbe9-41f3-b7bc-ac49ec637335.png)









### TIMING DIGRAMS  
Multiplexer
![image](https://user-images.githubusercontent.com/122356434/215397159-1df44155-ff7a-4543-9094-68e514d54f26.png)
![image](https://user-images.githubusercontent.com/122356434/215397228-beff39c2-ac52-4faa-b0f5-4cae751a8e14.png)
![image](https://user-images.githubusercontent.com/122356434/215397259-4e627371-7ea0-469a-a5fd-7be5e6324f4f.png)
![image](https://user-images.githubusercontent.com/122356434/215397294-7f0ecab4-2b10-4525-840c-0122e530474d.png)

De Multiplexer
![image](https://user-images.githubusercontent.com/122356434/215397333-5f66b4b4-a686-494b-a47a-15d1ef2d84d9.png)


### TRUTH TABLE

Multiplexer
![image](https://user-images.githubusercontent.com/122356434/215397379-afcb3892-d043-4019-8497-68b9ed22ee8b.png)

Demultiplexer
![image](https://user-images.githubusercontent.com/122356434/215397480-1ee75b87-7bd2-46f8-8dc3-42506489e047.png)




### RESULTS
Hence 4x1 Multiplexer and 1x4 Demultiplexer is been implemented and verified using verilog programming and its output are validated.
