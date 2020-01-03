---
layout: page
title:  "Introduction to electronics"
date:   2018-12-07
author: Andrew Sleigh
---

Inputs and outputs on a breadboard

<!--more-->

## Prep for this week's class

* If you’ve never done any electronics before, read an introductory tutorial or watch a video to get some of the basics:
	* [SparkFun have great tutorials](https://learn.sparkfun.com/tutorials)
	* Lots on YouTube, e.g. [Beginner Electronics - YouTube](https://www.youtube.com/playlist?list=PLah6faXAgguOeMUIxS22ZU4w5nDvCl5gs)

## Baseline 

Who has:
* Made something with electronics?
* Used an Arduino, Microbit or other microcontroller?
* Written any code?

## This week:

* Tour of some basic components
* Breadboards and jumpers
* Circuit basics
* Connecting a circuit to a microcontroller
* Programming a microontroller to respond to input and do something with it


## Components
### Wire
Ribbon cable used for ISP headers - and post-milling board edits – [picture]({{ site.baseurl }}/assets/ribbon-wire.jpg)  
Also, headers (mechanical convenience)

### Buttons and Switches

Surface mount versions for circuits – [picture]({{ site.baseurl }}/assets/button.jpg)  
Momentary buttons - “N.O.” make a circuit when pressed (example use: connect a chip's reset pin to GND)  
You might want to use [cool buttons](http://blog.presentandcorrect.com/27986-2) for UI elements – [picture]({{ site.baseurl }}/assets/68426c45c8b5.jpg)

### Resistors

* Value measured in Ohms (1 Ohm, 5 kOhm, 4k7 Ohm, etc.)
* Limit the flow of current
* Ohm’s law: I = V/R

[Symbol]({{ site.baseurl }}/assets/resistor-symbol.png)


Uses often include:
* Regulate current to LEDs – [picture]({{ site.baseurl }}/assets/resistor-circuit.PNG)
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

[Symbol]({{ site.baseurl }}/assets/capacitors.png)

Uses:
* Filtering high-frequency noise from ICs (“decoupling” or “bypass” capacitors)
* Supplying current to IC pins very quickly (e.g. when you ask it to switch on and off in your program)
* Create pulses at specific time intervals (with resistors)

Sizes:
* 1206 SMD 
* Bigger capacitors often polarised

More: <https://learn.sparkfun.com/tutorials/capacitors>

<!-- ### Crystals and resonators

Used to tell time.   
Crystals are very accurate, but need 2 capacitors.  
Resonators are more convenient, but less accurate (could cause problems for your IC, e.g. for fast serial comms).  
IMHO: crystals are easier to solder, even with caps

Uses:
* External clock for microcontroller (IC) -->

### Diodes

Conducts only in one direction (as shown in circuit symbol)  
Current flows from anode (+) to cathode (-) (alphabetical)

[Symbol]({{ site.baseurl }}/assets/diode.PNG)


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


:construction:
### Tilt switches, Hall effect sensors, bend sensors, ...
### Accelerometers
### Capacitive sensors
### Temperature sensors
### Potentiometers


### Microcontrollers

A whole circuit inside one package: a computer, analogy to digital convertors, clock, PWM outputs, memory, switches, etc, etc.

<!-- We’ll mostly use ones from Atmel: 

* ATtiny [44](https://www.microchip.com/wwwproducts/en/ATtiny44)/45, 84/85
* ATmega 328p (Arduino Uno)
* ATmega 32u4 (Arduino Leonardo, USB)

[Datasheets](http://ww1.microchip.com/downloads/en/DeviceDoc/doc8006.pdf) - learn to love them! 


And many more ... -->


### Further reading

Fab Academy:
* Input devices: <http://academy.cba.mit.edu/classes/input_devices/index.html>
* Output devices: <http://academy.cba.mit.edu/classes/output_devices/index.html>
Electronics bible: [Paul Horowitz, Winfield Hill-The Art of Electronics-Cambridge University Press (2015)](https://www.amazon.co.uk/Art-Electronics-Paul-Horowitz/dp/0521809266/ref=dp_ob_title_bk)
Good hobbyist starting point: [Charles Platt’s Electronics Pages: Books Available](http://www.plattelectronics.com/books.html)




## Assignment

Use a breadboard, jumper wires and input and output devices to build an interactive device based around a Microbit.
Program your Microbit to respond to input and produce an off-device output.

If you find this easy, do something more ambitious!


### What do I need to do to pass? (40%)


Document all your work on your student blog, with photos and videos to show what you did, what went wrong, and how you fixed it. 

Cite external sources where you have used someone else's work.

### Extra credit (50-100%)

* Replicate the circuit and program logic with an Arduino
* Use multiple input or output devices
* Create a higher fidelity prototype that could be embeedd in a devices or worn on clothing

Show your research and include reflection on the process, and other resources you have found. 

---

## Materials we need this week

Microbits
Microbit breadboard connectors
Breadboards

Through-hole I/O devices

