## 2025-05-19
Four years ago, I built a custom clock with off-the-shelf parts (Arduino Nano, DS3231 breakout, 32x8 MAX7219 LED Matrix, all on a breadboard with 2 buttons). Although it has worked very reliably, only needing a few battery replacements and resetting the nano a few times, I want to make a custom solution.

![A simple clock with a LED matrix with the current time in a blue case. An Arduino Nano and other components are in the background.](./assets/20250519_132615.jpg)
*the current solution ✨*

### Plans
Displays: https://www.aliexpress.com/item/1005007029570407.html
bicolour 8x8 led matrix !! (Red Yellow Green CC)
![](./assets/S4433b8a162e44ab2af2c7316474f55a4q.jpg) \
Controller: Holtek HT16K33A
https://www.holtek.com/webapi/116711/HT16K33Av102.pdf
likely going to take inspiration from here: 
- https://www.adafruit.com/product/902
- https://learn.adafruit.com/adafruit-led-backpack/bi-color-8x8-matrix

Display Schematic (from Adafruit):
![](./assets/image13134.png)

Using these connections (no STEMMA connectors, just 4 ICs wired on a PCB to same I2C bus with different addresses hard-set on each IC), I will probably make a similar PCB layout with these segments + a microcontroller (possibly a SMD rp2040-zero) with a RTC module and battery slot + controlls for time adjustment and screen brightness controll + an alarm feature. \
I could also use an ESP32 XIAO board and make a feature to add alarms with your phone (maybe also experiment with Zigbee?). I shall see. \
All rough ideas for now, I have some parts in mind but I will likely have to order the screens and a HT16K33(A) breakout board (https://www.aliexpress.com/item/1005006831500717.html) to see if this idea is feasible. If it is, this will be pretty epic.

## 2025-05-22
Ordered the 10 pack of LED matricies and the HT16K33 breakout board. I'll prototype with it and build a schematic based on that. The cost of the other components will likely not be much. Not much else for today.

## 2025-05-26
I found this video a few days ago that popped into my YT rec: https://www.youtube.com/watch?v=7fNYj0EXxMs. The PCB design was shown for a few seconds and its quite interesting since he uses the same Holtek driver (along with an I2C address translator; LTC4316) to drive a row of 8 displays, each with 20 pins: 
![](./assets/coolmatrix.png)
I'll try and see what magic was performed here (since idk much about this) and see if I can emulate it !!