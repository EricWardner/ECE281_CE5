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
