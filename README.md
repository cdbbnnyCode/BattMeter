## BattMeter
![PCB preview](/images/board.png)  
BattMeter is a simple voltage meter for FTC batteries. The voltage ranges can be adjusted by changing the values of
r1, r2, r3, r4, and r5 (see [v1.2_voltages.txt](/v1.2_voltages.txt) for default resistor values).  
The board has an XT30 plug to connect REV batteries directly. If you have a different type of connector on your batteries, you can:
* Use an adapter plug
* Use a short length of wire and solder your connector onto that (recommended for crimped connectors like Tamiya and Anderson Powerpoles)
* Modify the board to fit your connector

### Usage
To edit these files, you need Autodesk Eagle. If you just want to fabricate a board, you should be able to find Gerber files under
the Releases page. You can find a list of the components you need under [bom.txt](/bom.txt).  
The PCB design and schematic are licensed under the [Creative Commons Attribution-ShareAlike 4.0 License](https://creativecommons.org/licenses/by-sa/4.0/).

### How it works
This meter uses four op-amp comparators to turn on the LEDs at specific input voltages.  
![Input and regulation](/images/regulator.png)  
A voltage divider reduces the battery voltage to somewhere around 5V, and the regulator provides a (reasonably) fixed 5V reference.  
![A single comparator](/images/opamp.png)  
The chain of resistors (r1, r2, r3, r4, and r5) drop the regulated voltage at specific steps, and the op-amps compare the scaled
battery voltage with this voltage. The logic is inverted--the input voltage is connected to the inverting input--because the LED
turns on when the op-amp's output is pulled to GND.  
