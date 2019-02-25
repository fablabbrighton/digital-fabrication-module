---
layout: page
title:  "Guide: Finding components for a FabISP Programmer "
date:   2019-02-25
author: Andrew Sleigh
---

How do you find parts for a new FabISP Programmer board?

<!--more-->

Refer to the [original docs](http://fab.cba.mit.edu/classes/863.16/doc/projects/ftsmin/index.html) for a full explanation.

## Components

See the original circuit diagram: 

![isp-pcb_full.png]({{ "/assets/isp-pcb_full.png" | relative_url }})

And schematic:

![fabisp-schematic.png]({{ "/assets/fabisp-schematic.png" | relative_url }})


## B.O.M.

1x ATtiny45 or ATtiny85
2x 1kΩ resistors
2x 499Ω resistors
2x 49Ω resistors
2x 3.3v zener diodes
1x red LED
1x green LED
1x 100nF capacitor
1x 2x3 pin header


## Finding the parts

Circuit ID,BOM,Bin label,markings
U1,ATtiny45,ATtiny45V, TINY45V
R1 and R6,1kΩ resistors,1kOHm Res,1001
R2 and R5,499Ω resistors,499Ohm res,4990
R3 and R4,49Ω resistors,49.9Ohm res,49R9
D1 and D2, 3.3v zener diodes,Zener Diode 3.3v, cathode marked
D4,red LED,LED Red 1206,cathode marked
D3,green LED,LED Green 1206, cathode marked
C1,100nF capacitor,0.1 uF Cap, none
ISP,2x3 pin header,2x3 ISP, none


## Making a reference sheet

![parts-sheet.jpg]({{ "/assets/parts-sheet.jpg" | relative_url }})

