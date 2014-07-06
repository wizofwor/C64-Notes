#Branches

##Unconditional Branch Instructions

JMP - Jumps to another location  
JSR - Jump to a subroutine  
RTS - Returns from a subroutine

## Conditional Branch Instructions

Conditional branch instructions depends on CPU status registers. C, Z, N and V (Carry, Zero, Negative and Overflow)
+ C is set when the add produced a carry, or if the subtraction produced a borrow. Also holds bits after a logical shift.
+ Z is set when the result of the last operation (load/inc/dec/add/sub) was zero.
+ N is set when bit seven of the accumulator is set
+ V is set when the addition of two like-signed numbers or the subtraction of two unlike-signed numbers produces a result greater than +127 or less than -128.

Instruction | Branch on... | When... 
---|---|---
BCC  | Branch on Carry Clear|       C = 0  
BCS  | Branch on Carry Set|         C = 1  
BEQ  | Branch on EQual to zero|     Z = 1  
BNE  | Branch on Not Equal to zero| Z = 0  
BMI  | Branch on MInus|             N = 1  
BPL  | Branch on PLus|              N = 0  
BVS  | Branch on oVerflow Set|      V = 1  
BVC  | Branch on oVerflow Clear|    V = 0  
   
## Compare Instructions


**CMP** compares memory and accumulator. CPX and CPY do the same thing for X and Y registers. Take look at following table:

Comparison | N | Z | C
---|---|---|---|---
accumulator < memory | 1 | 0 | 0
accumulator = memory | 0 | 1 | 1
accumulator > memory | 0 | 0 | 1 

   
**BIT** compares memory with accumulator. Actually it perform AND operation between accumulator and memory but doesn't manupulate neither. Only status flags are effected.

+ N receives the initial value of memory bit 7.
+ V receives the initial value of memory bit 6.
+ Z is set when the result of the AND is zero, otherwise reset
