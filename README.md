# SRAM
6T SRAM stands for static random access memory using total 6 Transistors, where 4 transistor are of nmos and 2 transistors of pmos here. 
In addition to that we are having wordline(WL) and bit lines. Q and Qbar are the outputs of the respective inverters. 
There are 3 operations of 6T SRAM: Read, Hold and Write. There are two precharged capacitor,it will be used in read and write operation. 
In Hold condition wordline will be 0 because when wordline =0 then the M5 and M6 transistors will be OFF and the access will be lost to bit and bitbar line, 
so the memory will be in hold state and data is held in the latch condition.<br>

When wordline is 1, both M5 and M6 transistor will be ON, this means that we can access bit and bitbar lines(these M5 and M6 are excess transistors that 
are used to make sure that we can use the input and output). 
In this condition read and write are possible because bit and bitbar are active. Bit and bitbar plays the main role here, bit and bitbar will act as input line when we have to write into the memory. 
If we have to perform read operation from the memory ,bit and bitbar will as output line.<br>

READ OPERATION: For reading operation,we have to make word line as 1. Then excess transistors M5 and M6 will be ON and we will use bit and bitbar as the output lines. 
If we have memory value Q=1 then drain point of the transistor M5 will be high and source has already at VDD, so capacitor will not discharged because of no voltage 
difference between of source and drain of the transistor there. But,Qbar=0 so in this case there is voltage difference in the source and drain point of the M6 transistor,
So capacitor will discharge here. That means voltage of bit bar will decrease. WE have to send this value of bit and bitbar to the sense amplifier, now the sense 
amplifier will act as acomparator and when comparator will say if bitbar value decreases then output should be 1. If this will happen then we have successfully 
read from the memory.<br>

WRITE OPERATION: For writing operation ,we have to make word line as 1. Then excess transistors M5 and M6 will be ON, now we can acess the bit and bitbar lines and
we will use bit and bitbar as the input lines here. Here, the memory value Q=0 and Qbar=1. As bit and bitbar are input lines , so we have control over it.
So I have made this bitbar line as ground because due to Qbar=1, transistor M6 will be ON and there will be voltage difference between source and drain of 
the transistor of M6 and then capacitor will discharge and voltage at bitbar will decrease. If voltage is less than the threshold voltage of M2 transistor,
then M2 transistor will be OFF and M3 transitor will be ON, so that output of this iverter Q=1.(in starting i had taken Q=0 but here I have made it Q=1). 
Now we have write successfully in the memory.<br>

Here, I am performing write operation of the 6T SRAM.<br>

Schematic Diagram of 6T SRAM in LTspice 
![6T SRAM](https://user-images.githubusercontent.com/111113962/192131118-7088c4de-610a-469f-b88b-644c9210b7c5.jpg)

In this waveform I am showing the word line(blue) and bit line in green colour. Initially word line is high but after 15ns word line is low. As we discussed, when 
word line is low then we can not perform read and write operation,output will be retained as previous output but when word line is high we can perform the read and
write operation.<br>

Bit line waveform
![Bit_waveform](https://user-images.githubusercontent.com/111113962/192131149-02ae3583-a57a-4870-8566-50cb5cebcdb3.jpg)

In this waveform I am showing output of the memory. I am using red colour for showing the output waveform,here blue colour is word line. In our waveform, initially 
word line is 1, output will follow the same values as input or we can say output will follow the bit line which is showing in green colour(above) but after that word 
line is low so output will retain the previous value of Q, and again word line is continously 1 then output will follow exactly the same as bit line waveform.<br>

Output waveform
![output waveform of 6T SRAM](https://user-images.githubusercontent.com/111113962/192131168-00b5c385-5db9-4c32-8ffc-e4cceacd33fc.jpg)

