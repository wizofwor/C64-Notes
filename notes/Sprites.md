Sprite-MC

### Enable Sprites

VIC Register, $D015 enables the sprites: Least significant bit represents Sprite #0, most significan bit represent Sprite #7 and so on.

### Sprite Pointers

Sprite pointers are located at SCREEN-RAM+1016/1023, default value is $07F8–07FF

VIC reads sprite data as 64 byte block so, in order to sprite pointer for particular ADRESS should be ADRESS/64  


### Colors

Bit | Color | Adress
---|---|---
00 | Background |$D021
01 | Sprite-MC-Color1 | $D025
10 | Sprite-Color | $D027..)
11 | Sprite-MC-Color2 | $D026
