#C64 Memory Map

Default memory map of Commodore 64 priorites BASIC usage. However it is highly configarable for specific purposes. It is possible to cancel unnecassary ROM fields and reach underlying RAM.  

|  ADRESS 	| C64 Memory Map      |VIC Banks | $0001
|-----------|---------------------|----------|------
|$E000-$FFFF|	KERNAL ROM	        | Bank 3   | Bit #1
|$D000-$DFFF|	CHAR ROM / IO	      | "        | Bit #2
|$C000-$CFFF|	Free	              | "    |
|$A000-$BFFF|	BASIC ROM           | Bank 2    | Bit #0
|$7000-$9FFF| Free Basic Storage Area| "     |
|$3000-$6FFF|	"         "            | Bank 1   |
|$0800-$2FFF|	" 	      "            | Bank 0   |
|$0400-$07FF|	Screen Memory       |	 "      |
|$0200-$03FF|	OS & BASIC Pointers |	 "       |
|$0100-$01FF|	Enhanced Zero Page	|   "      |
|$0000-$00FF|	Zero Page	          |  "      |
* Between $1000-$17ff there is character generator rom. But is only visible to VIC
* Between $9000-$9FFF there is charackter generator rom shadow, which is also visible for VIC only. 
