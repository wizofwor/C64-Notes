#Timing



We have three different clock signal Color Clock, Dot Clock, and System Clock. Color Clock  

VIC-II can put a byte of data, means 8 pixels, on screen in each cycle. As the PAL screen is 504 pixels wide including borders, we need 504/8=63 cycle to draw each raster line. (or 520/8=65 cycle for NTSC)
