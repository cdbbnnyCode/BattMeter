## BattMeter
|insert image here|
BattMeter is a (very uncreative) name for a simple FTC battery meter. The voltage ranges can be changed by changing the values of
r1, r2, r3, r4, and r5 (see v1.2_voltages.txt for default resistor values).  

### Usage
To edit these files, you need Autodesk Eagle. If you just want to fabricate a board, you should be able to find Gerber files under
the Releases page.  
The PCB design and schematic are licensed under the Creative Commons Attribution-ShareAlike License. 

### How it works
This meter uses four op-amp comparators to turn on the LEDs at specific input voltages.  
|Input and regulation pic|  
A voltage divider reduces the battery voltage to somewhere around 5V, and the regulator provides a (reasonably) fixed 5V reference.  
|Op-amps pic|  
The chain of resistors (r1, r2, r3, r4, and r5) drop the regulated voltage at specific steps, and the op-amps compare the scaled
battery voltage with this voltage. The logic is inverted--the input voltage is connected to the inverting input--because the LED
turns on when the op-amp's output is pulled to GND.  
