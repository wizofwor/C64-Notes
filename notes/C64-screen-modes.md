
# VIC II Screen Modes                         
*based on c64 Programmers Referance        

Screen size is 40x25 char or 320 x 200 pixels
$d011 bit 5 controls bitmap mode
$d016 bit 4 controls multi color mode

Such that:

Screen Mode | $d011 | $d016
---|---|---
Hires text mode | $1b | $08
Multicolor text mode | $1b | $18
Hires bitmap mode | $3b | $08
Multicolor bitmap mode | $3b | $18
ECM text mode | $5b | $08

1.  Hires Text Mode:

   This is the default mode  
   screen is filled by characters described by screen_ram ($0400)   

   Each bit on character rom represent 1 pixel  
   0 -> screen color:  $d021  
   1 -> color ram  


2. Multicolor Text Mode
  
   bit pairs on character rom determines a pixel such that  
   00 -> background #0 $d021  
   01 -> background #1 $d022  
   10 -> background #2 $d023  
   11 -> color ram

3. ECM Text Mode

   Gives more control over the background colors but limited to 64 chars.
   
   character code  background color
   00xxxxxx        bg #0 $d021
   01xxxxxx        bg #1 $d022
   10xxxxxx        bg #2 $d023
   11xxxxxx        bg #3 $d024

4. Hires Bitmap Mode
   
   instead of color_ram, screen_ram is now used for color information
   and charater_ram used to hold bitmap data
  

5. Multicolor Bitmap Mode

   bit pairs represents pixel 
   00 -> bg #0 ($d021)
   01 -> upper 4 bits of screen memory
   10 -> lover 4 bits of creen memory
   11 -> color nyble
