Adress | Registers
---|---|---
$d000 - $d00f | Sprite coordinates (M0X,M0Y,M1X,M1Y,...)
$d010 | Extended bit for X position
$d011 | Control register 1
$d012 | Raster counter
$d013 | Lightpen X
$d014 | Lightpen Y

## Control Registers

$d011

 7 | 6 | 5 | 4 | 3 | 2 - 0
---|---|---|---|---|---|---|---
RST8 | ECM | BMM | DEN | RSEL |  YSCROLL

* YSCROLL: Vertical scroll
* RSEL: Text mode rows 24/25
* DEN:  Blank screen (when off)
* BMM:  Enable bitmap mode
* BMM:  Enable bitmap mode
* ECM:  Enable extended color text mode
* RST8: MSB of raster control register

$d016

 7 | 6 | 5 | 4 | 3 | 2 - 0
---|---|---|---|---|---|---|---
-  | -  | RES | MCM | CSEL | XSCROLL 

* XSCROLL: Horizonal scrol
* CSEL:  Text mode columnts 38/40
* MCM:  Enable multicolor mode
* RES:  Reset VIC
