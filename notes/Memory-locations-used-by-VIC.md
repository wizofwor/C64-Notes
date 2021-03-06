### VIC BANK SELECTION

Bank selection is a bit tricky:

```
lda $dd02   ;make sure Port A on CIA#2 is set to output
ora #03     ;
sta $dd02

lda $dd00   ;change banks
and #$fc
ora #$xx    ; xx = bank
sta $dd00
```
$dd00 | Bank | Adress Range 
---|---|---
%xxxxxx00 | -3* | $C000-$FFFF
%xxxxxx01 | 2   | $8000-$BFFF
%xxxxxx10 | 1*  |  $4000-$7FFF
%xxxxxx11 | 0   |  $0000-$3FFF (Default value)

*rom character set is not available in these banks

Do not forget, certain regions of Commodore 64 memory are used by ROM by default. If you want to utilise the adress range already occupied by ROM as RAM, you should disable ROM. Consult [memory map](https://github.com/wizofwor/C64-Notes/blob/master/Memory-Map.md) to see overlying Rom fields.

### SCREEN_RAM

C64 screen in text mode is formed by 40x25=1000 cells or characters. 'Screen ram' or 'screen memory' holds the pointers for each character cell. It is 1000 bytes long, but for the sake of simplicity, in memory it goes on multiples of 1024 = $0400. Upper 4 bits of $d018 controls the location of the screen memory.

Possible locations on of screen ram in VIC Bank 0

$D018 Value | Screen Ram | $D018 Value | Screen Ram 
---------|---------------|-------------|---------
%0000xxxx | $0000 | %1000xxxx | $2000
%0001xxxx | $0400*| %1001xxxx | $2400
%0010xxxx | $0800 | %1010xxxx | $2800
%0011xxxx | $0c00 | %1011xxxx | $2c00
%0100xxxx | $1000 | %1100xxxx | $3000
%0101xxxx | $1400 | %1101xxxx | $3400
%0110xxxx | $1800 | %1110xxxx | $3800
%0111xxxx | $1c00 | %1111xxxx | $3c00

*default

### COLOR_RAM

Color memory cannot move. It is always between $d800 - $dbe7


### CHARACTER_MEMORY

Character memory location is controlled by bits 3,2 and 1 of $d018
Character set stored in 2K blocks such as:

$d018 |Character Memory
----------|--------------
%xxxx000x | $0000 - $07ff
%xxxx001x | $0800 - $0fff
%xxxx010x | $1000 - $17ff *
%xxxx011x | $1800 - $1fff
%xxxx100x | $2000 - $27ff
%xxxx101x | $2800 - $2fff
%xxxx110x | $3000 - $37ff
%xxxx111x | $3800 - $3fff

*Rom image in bank 0 and 1 (default)
