---
layout: page
title:  "Week 5: Electronics design"
date:   2018-12-14
---

Designing, building and testing a circuit

<!--more-->



## Prep for this week's class

* Installed and licensed Autodesk Eagle software: [Free Software for Students & Educators](https://www.autodesk.com/education/free-software/eagle)
	* Verified that you can open up and use the software.
	* Having difficulty getting the educational version? Try the [free hobbyist version](https://www.autodesk.com/products/eagle/free-download)

* Watch the corresponding Fab Academy lecture. We'll be covering part of this content:
	* Fab Academy lecture notes: <http://academy.cba.mit.edu/classes/electronics_design/index.html>  
	* Lecture from 2018: [Fab-20180228D_Lesson06: electronics design](http://fab.academany.org/2018/lectures/fab-20180228.html)

* If you’ve never done any electronics before, read an introductory tutorial or watch a video to get some of the basics:
	* [SparkFun have great tutorials](https://learn.sparkfun.com/tutorials)
	* Lots on YouTube, e.g. [Beginner Electronics - YouTube](https://www.youtube.com/playlist?list=PLah6faXAgguOeMUIxS22ZU4w5nDvCl5gs)

## Baseline 

Who has:
* Made something with electronics?
* Used an Arduino?

- - - -

This week:

* Tour of some basic components
* Learn how to draw a circuit in Eagle
* Assignment: draw a circuit board, ready for milling (ending up where we started last week).
* (Make and test it)
* Next week, program it

- - - -

## Components
### Wire
Ribbon cable used for ISP headers - and post-milling board edits – [picture]({{ site.baseurl }}../assets/ribbon-wire.jpg)  
Also, headers (mechanical convenience)

### Buttons

Surface mount versions for circuits – [picture]({{ site.baseurl }}../assets/button.jpg)  
Momentary buttons - “N.O.” make a circuit when pressed (example use: connect a chip's reset pin to GND)  
You might want to use [cool buttons](http://blog.presentandcorrect.com/27986-2) for UI elements – [picture]({{ site.baseurl }}../assets/68426c45c8b5.jpg)

### Resistors

* Value measured in Ohms (1 Ohm, 5 kOhm, 4k7 Ohm, etc.)
* Limit the flow of current
* Ohm’s law: I = V/R

[Symbol]({{ site.baseurl }}../assets/resistor-symbol.png)

Uses often include:
* Regulate current to LEDs – [picture]({{ site.baseurl }}../assets/resistor-circuit.PNG)
* Keep pins high or low (pull-up/pull-down) without current flowing

Sizes: 
* We use 1206 (0.**12**”× 0.**06**”) 
* Hand solderable
* You can get a trace between the two ends

More: [Resistors - learn.sparkfun.com](https://learn.sparkfun.com/tutorials/resistors/all)

### Capacitors

Store charge, and release it when the voltage across the cap reaches a specific level  
Q (charge stored) = C (capacitance) x V (voltage across plates)  
Value of capacitance (amount of charge it can store): Farad (F, nF, pF, uF, etc.)

[Symbol]({{ site.baseurl }}../assets/capacitors.png)

Uses:
* Filtering high-frequency noise from ICs (“decoupling” or “bypass” capacitors)
* Supplying current to IC pins very quickly (e.g. when you ask it to switch on and off in your program)
* Create pulses at specific time intervals (with resistors)

Sizes:
* 1206 SMD 
* Bigger capacitors often polarised

More: <https://learn.sparkfun.com/tutorials/capacitors>

### Crystals and resonators

Used to tell time.   
Crystals are very accurate, but need 2 capacitors.  
Resonators are more convenient, but less accurate (could cause problems for your IC, e.g. for fast serial comms).  
IMHO: crystals are easier to solder, even with caps

Uses:
* External clock for microcontroller (IC)

### Diodes

Conducts only in one direction (as shown in circuit symbol)  
Current flows from anode (+) to cathode (-) (alphabetical)

[Symbol]({{ site.baseurl }}../assets/diode.PNG)


Uses: 
* Prevent current going in the wrong direction (e.g. if you connect a battery backwards)
* Often used in AC/DC convertors  

Types:
* Signal diode
* Specialised: Schottkey diode, Zener diode 
* LED: emits light and happiness

Diodes are polarised: bar on the symbol is the same as on the package (cathode)  
Diodes have no internal resistance, so can draw all the current available, and blow up  
So use a current-limiting resistor (e.g. 100 Ohm, 1K Ohm) - very common with LEDs


<!-- 
### Transistors

MOSFETs (Metal Oxide Semiconductor Field Effect Transistor)
Used to switch current in high power applications

Regulators
Turn a variable voltage into a fixed one (e.g. 5V for your IC)
Dissipate heat 

Op Amp 
Amplify current or voltage
Mostly now built into microcontrollers
 -->

### Microcontrollers

A whole circuit inside one package: a computer, analogy to digital convertors, clock, PWM outputs, memory, switches, etc, etc.

We’ll mostly use ones from Atmel: 

* ATtiny 44/45, 84/85
* ATmega 328p (Arduino Uno)
* ATmega 32u4 (Arduino Leonardo, USB)

Datasheets - learn to love them! 


And many more ...


### Further reading

Fab Academy:
* Input devices: <http://academy.cba.mit.edu/classes/input_devices/index.html>
* Output devices: <http://academy.cba.mit.edu/classes/output_devices/index.html>
Electronics bible: [Paul Horowitz, Winfield Hill-The Art of Electronics-Cambridge University Press (2015)](https://www.amazon.co.uk/Art-Electronics-Paul-Horowitz/dp/0521809266/ref=dp_ob_title_bk)
Good hobbyist starting point: [Charles Platt’s Electronics Pages: Books Available](http://www.plattelectronics.com/books.html)


## Drawing circuits
### Overview

#### Libraries of parts
Part: e.g. a 10k resistor
Package: surface mount or through hole, size, etc.
Specs: current it can handle, accuracy, etc.
Libraries handle all this for you.

![eagle-library.png]({{ site.baseurl }}{{ "/assets/eagle-library.png" | relative_url }})


There is an Eagle library of parts in the Fablab inventory:
[eagle · master · pub / libraries · GitLab](https://gitlab.cba.mit.edu/pub/libraries/tree/master/eagle)

1. Download: <https://gitlab.cba.mit.edu/pub/libraries/blob/master/eagle/fab.lbr>
2. Make sure it’s named `fab.lbr`
3. Move to your Eagle Library location. Something like: `/Users/YourName/Documents/EAGLE/libraries/`
4. Open the Eagle Control Panel (under `Window` menu)
5. Find library you added, right click and select `Use`

![eagle-add-lib.png]({{ site.baseurl }}{{ "/assets/eagle-add-lib.png" | relative_url }})


Go to a Schematic, add a part (which opens the Library window), and you should be able to select parts from the `fab` library:

![eagle-part-in-fab-library.png]({{ site.baseurl }}{{ "/assets/eagle-part-in-fab-library.png" | relative_url }})



#### Schematic
Logical structure of a circuit.  
How are the components connected.  
Abstract, not a visual representation.

![eagle-schematic.png]({{ site.baseurl }}{{ "/assets/eagle-schematic.png" | relative_url }})

My schematic for Hello World board.  
Green lines show connections between parts.  
Parts are in red - notice chip doesn’t look like that.   
Once you’ve got used to Eagle, its easier to connect points by names instead of lines.

**Common tools:**

![eagle-sch-toolbar-labelled-alpha.png]({{ site.baseurl }}{{ "/assets/eagle-sch-toolbar-labelled-alpha.png" | relative_url }})


#### Board layout

Where the components go on the board, and how to route traces (connections between parts) between them.  
How to satisfy the requirements of the schematic, within the constraints of the fab process (aka design rules). Mainly: how thin can traces be, how close together can they be.  
Layers: we’ll only make single layer boards.


Tools are frustrating at first. Eventually satisfying, like solving a puzzle.  
Art: place parts well, process of trying placement and routing, ripping it up, try again.  
Tricks: rotating parts, or running traces underneath.

![eagle-board-layout-airwires.png]({{ site.baseurl }}{{ "/assets/eagle-board-layout-airwires.png" | relative_url }})


Yellow lines are “Airwires”.   
Job here is to convert the airwires into traces. 

![eagle-board-layout.png]({{ site.baseurl }}{{ "/assets/eagle-board-layout.png" | relative_url }})


Red lines are traces.

**Common tools:**


![eagle-brd-toolbar-labelled-alpha.png]({{ site.baseurl }}{{ "/assets/eagle-brd-toolbar-labelled-alpha.png" | relative_url }})

This *is* a visual representation. 

**<span class="wip">WIP</span> Other tools:**

**DRC**  
**ULP**




#### Export traces and outline

Adjust and re-colour to get your milling source file:

![ech-hello-world-v7-mod-traces3-01.png]({{ site.baseurl }}{{ "/assets/ech-hello-world-v7-mod-traces3-01.png" | relative_url }})


Optional step, there are other ways of getting your circuit image out of Eagle.

This lets you adjust traces, hide layers, resize the board, add vector art, etc.

Make sure physical size remains constant.

<span class="wip">WIP: Does this work in Inkscape??</span>


### 4. Export PNG Image
* Uncompressed format
* Very high resolution: 1000dpi, because we’re machining at a resolution of 1/1000 of an inch
* Back and white (1bit)
* Editable - creatively, or to fix milling problems

[Raphael Schaad - How to Make (almost) Anything](http://fab.cba.mit.edu/classes/863.15/section.CBA/people/Schaad/week6-electronics-design.html)
![](Electronics%20design/echo-hello-world-schaad-hand.jpg)


### 5. Verify
Print out your PNG at 100% and place some components on the printout. 
Do they fit?
Are there overhangs that interfere, or bits you need to access that you can’t reach (e.g. a USB or power socket).

![IMG_0235.jpg]({{ site.baseurl }}{{ "/assets/IMG_0235.jpg" | relative_url }})


<span class="wip">WIP</span> Need to cover outlines too.

### 6. Fabricate
Follow same process as last week: mill, solder, test, program

## Testing

Multimeter - check for continuity or shorts.  
Oscilloscope - measure voltage over time, see what signals pins are sending.

- - - -

## Assignment

<span class="wip">WIP: explanation of each component (about 1m06s in video)</span>

<span class="wip">WIP: Do we need the FTDI header? Probably only for serial testing with FTDI cable</span>

1) Redraw the Hello World board, starting with [Neil’s circuit](http://academy.cba.mit.edu/classes/embedded_programming/hello.ftdi.44.png):

![hello.ftdi.44.png]({{ site.baseurl }}{{ "/assets/hello.ftdi.44.png" | relative_url }})

Use a library in Eagle to get all these parts (look at the part bins here to see what we have).  
Draw a schematic and board layout.  
Export a millable png file of the traces and outline.
How compact can you make it? ( = less waste, less milling time)

2) Make the board

<span class="wip">WIP</span>

3) Upload a pre-written program to the board to test that it works

Options:
a) Use the Atmel programmer (Fall-back) – [picture]({{ site.baseurl }}../assets/atmel-ice-connection.png)

See [Atmel ICE docs](http://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-ICE_UserGuide.pdf):  
3.1. Connecting to AVR and SAM Target Devices  
3.7. Connecting to an SPI Target  



b) Use the FabISPs we made last week

See separate instructions.

<span class="wip">WIP: compile these</span>

c) Use another pre-made programmer  - will these work?

e.g. FTDI cable or a breakout board

<span class="wip">WIP: test these</span>

Program
If you’ve added a button and LED, you can try the standard Arduino blink sketch
Otherwise try [Neil’s serial test](http://academy.cba.mit.edu/classes/electronics_design/index.html) using RX and TX pins on the FTDI header ([code](http://academy.cba.mit.edu/classes/embedded_programming/hello.ftdi.44.echo.c)).




### What do I need to do to pass?

Redraw the board without any additional components in Eagle and generate a PNG file suitable for milling.

Document all your work on your student blog, with photos and videos to show what you did, what went wrong, and how you fixed it. Cite external sources where you have used someone else’s work.

### Extra credit

Customise the board and then draw your custom version.

e.g. Add a button and an LED (with current-limiting resistor) to PB2 and PB7. (Both of these go from the pin on the chip (which is high voltage, aka VCC) to GND.)


Whether you've customised the board or not, mill and test the board by uploading a program.



## Source material / further reading/watching

* Fab Academy lecture notes: <http://academy.cba.mit.edu/classes/electronics_design/index.html>  
* Lecture from 2018: [Fab-20180228D_Lesson06: electronics design](http://fab.academany.org/2018/lectures/fab-20180228.html)
* [SparkFun tutorials](https://learn.sparkfun.com/tutorials)
* Electronics books:
	* Bible: [Paul Horowitz, Winfield Hill-The Art of Electronics-Cambridge University Press (2015)](https://www.amazon.co.uk/Art-Electronics-Paul-Horowitz/dp/0521809266/ref=dp_ob_title_bk)
	* Good hobbyist starting point: [Charles Platt’s Electronics Pages: Books Available](http://www.plattelectronics.com/books.html)



## Materials we need this week

* All components for board we make
* Atmel programmer or working FabISPs
* …?



### Failsafe for next week

Commercial Arduinos we can program.

