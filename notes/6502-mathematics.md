//following code might me incomplete

###Add with Carry
```ASM
  LDA $0400 
  CLC         ;clear carry  
  ADC #$xx 
  STA $0400
  BRK
```

###Subtract with Carry
```ASM
  LDA $0400 
  SEC         ;set carry 
  SBC #$1B 
  STA $0400 
  BRK
```  
###Multiply by 2
```ASM
  LDA $0400 
  ASL #$xx 
  STA $0400
  BRK
```  
###Divide by 2
```ASM
  LDA $0400 
  LSR #$xx 
  STA $0400
  BRK  
```
###Multiply by 3
```ASM
  LDA $0400
  ASL 
  CLC 
  ADC $0400 
  STA $0400 
  BRK
 ``` 
