Sprite-MC

### Enable Sprites

VIC Register, $D015 enables the sprites

    1111 1111
    |||| |||+-
    |||| ||+--
    |||| |+---
    |||| +----

Bit | Color | Adress
---|---|---
00 | Background |$D021
01 | Sprite-MC-Color1 | $D025
10 | Sprite-Color | $D027..)
11 | Sprite-MC-Color2 | $D026
