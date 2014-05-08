ECE281_CE5
==========
###Simple MIPS Assembly Program
initialize registers $S0 and $S1 with the decimal values 44 and -37 respectively. Use a register instruction to add these values together and store the result in $S2. Finally you will write an instruction that will store $S2 to the hexadecimal memory address x54.

```MIPS
# $s0 = a
 addi $s0, $0, 44   # a = 44
 
# $s1 = b
 addi $s1, $0, -37   # a = -37
 
# a + b = c
 add $s2, $s0, $s1      # c = $s2
 
# store c
 sw $s2, 0x54($0)       # c => 0x54
```

###Machine Code
|Instruction     |  op  |  rs  |  rt  |  immediate |   Hex Code|
|----------------|------|------|------|----------------|-------|
|```addi $s0, $0, 44```|001000|00000 |10000 |0000000000101100|0x2010002C|
|```addi $s1, $0, -37```|001000|00000 |10001 |1111111111011011|0x2011FFDB|

|Instruction      |  op  |  rs  |  rt  |  rd  | shamt| funct|Hex Code|
|-----------------|------|------|------|------|------|------|----------|
|```add $s2, $s0, $s1```|000000|00000 |10001 |10011 |00000 |100000 |0x02119020|

|Instruction     |op    |  rs  |  rt  |   immediate    | Hex Code|
|----------------|------|------|------|----------------|--------|
|```sw $s2, 0x54($0)```|101011|00000 |10010 |0000000001010100|0xAC120054|

######Simulation
The given waveform file initially did not work with my created testbench. Looking in the waveform file I noticed in the XML that the filepaths which referenced the desired processes used the name "mips_tb" as the name for the testbench. 
```XML
<wvobject fp_name="/mips_tb/uut/dp/rf/wd3" type="array" db_ref_id="1">
```
I made a new testbench with this name and the simulation worked!
(I also sent an email to the class explaining this fix)

![alt tag](https://raw.githubusercontent.com/EricWardner/ECE281_CE5/master/sim_capture.PNG)
