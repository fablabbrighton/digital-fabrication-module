---
layout: page
title:  "Introduction to electronics"
date:   2018-12-07
author: Andrew Sleigh
---

Inputs and outputs on a breadboard. Connecting inputs and outputs to a Microbit.

<!--more-->

## Prep for this week's class

* If you’ve never done any electronics before, read an introductory tutorial or watch a video to get some of the basics:
	* [SparkFun have great tutorials](https://learn.sparkfun.com/tutorials)
	* Lots on YouTube, e.g. [Beginner Electronics - YouTube](https://www.youtube.com/playlist?list=PLah6faXAgguOeMUIxS22ZU4w5nDvCl5gs)

<!-- 
## Baseline 

Who has:
* Made something with electronics?
* Used an Arduino, Microbit or other microcontroller?
* Written any code? -->

## This week:

* Tour of some basic components
* Circuit basics
* Connecting a circuit to a microcontroller
* Programming a microontroller to respond to input and do something with it


## Electronics basics

[Daniele Ingrassia presentation]({{ site.baseurl }}/assets/file/Electronics-Design.pdf)

## Components
<!-- ### Wire
Ribbon cable used for ISP headers - and post-milling board edits – [picture]({{ site.baseurl }}/assets/ribbon-wire.jpg)  


 -->

### Breadboards

Essentially some short wires pre-set in a convenient configuration

* What's significant and what isn't on the breadboard
* Internal wiring

![]({{ site.baseurl }}/assets/breadboards_side_by_side.jpg)  

* Also, headers (mechanical convenience)

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
<!-- 
Sizes: 
* We use 1206 (0.**12**”× 0.**06**”) 
* Hand solderable
* You can get a trace between the two ends -->

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
<!-- 
Sizes:
* 1206 SMD  -->
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

### Analog sensors

e.g. 
* Tilt switches 
* [Hall effect sensors](https://www.electronics-tutorials.ws/electromagnetism/hall-effect.html)
* Bend sensors
* Accelerometers
* Capacitive sensors
* Temperature sensors
* Potentiometers


When you're detecting something using an analog sensor and a Microbit (or Arduino) what you're actually measuring is the voltage at the pin where you plug the sensor in. 

The sensor itself usually changes resistance in response to some condition (heat, flex, humidity, magnetic force, etc.)

Most work by dividing a voltage by a variable amount (e.g. potentiometer). In some cases, you have to provide 0V and VCC (e.g. 3V or 5V) across the sensor to build your own [voltage divider](https://electronics.stackexchange.com/questions/417036/why-is-a-voltage-divider-used-when-reading-analog-sensors) (e.g. for a flex sensor)

* Analog vs digital iputs and outputs
* Possible values
* Calibrating sensors - e.g. for wearables


<hr/>



## Using External Inputs and Outputs ("IO") with Microbit



### :wrench: Exercise: Light an LED with just 3V and GND pins

No coding required.

Consult the pinout to see which pins are  

### :wrench: Exercise: Light an LED with signal and GND pins

Write some code to send a digital high signal to one of the pins, and connect the LED between this pin and GND.

Digital value 1 = "high" = 3V


![]({{ "/assets/microbit-pins.png" | relative_url }})


Note pinout diagram (of Microbit and of Breadboad connector)
* Note some pins interfere with LED Matrix
* back pins of connector do not go sequentially!

https://microbit.org/guide/hardware/pins/
> pin 3 is shared with some of the LEDs on the screen of the BBC micro:bit, so if you are using the screen to scroll messages, you can’t use this pin as well.


### :wrench: Exercise: Connect a sensor or control and control an output

### What you'll need

* Microbit
* USB Cable
* Breadboard
* Breadboard adapter

* External input: sensor, potentiometer, button
* External output: LED, OLED screen, LCD Screen, motor, buzzer, relay, servo



### :wrench: Exercise: Go further

Try other sensors, e.g. environmental sensor, flex sensor


### Potentiometer

http://www.multiwingspan.co.uk/micro.php?page=pot

> The potentiometer will give you a reading from 0 - 1023. If you divide that number by 4, you can use the reading to set the brightness of the LED matrix.
You could draw a series of images. Turning the potentiometer could then allow the user to select or scroll through the images displayed on the LED matrix.
Use some IF statements or the MAP block to convert your potentiometer reading into a number that you can use to move a sprite across one axis of the matrix. Add a second potentiometer and you have both directions.
A potentiometer and buzzer can be used. Convert the potentiometer reading into a number that you can use to play a tone on the buzzer. Mix in some button action if you want to be able stop and start the buzzing freely

Write pot reading to console and to screen
https://makecode.microbit.org/_7Ar65X3woDih
Should change brightness instead!

Switch LED on or off at threshold
https://makecode.microbit.org/_dHrJxy14mYLy

Control 3 LED trafic lights with pot
https://makecode.microbit.org/_4LUCadhhsc79


### Flex sensor

Only has 2 pins!
Need to make a voltage divider.

Basic serial reading:
https://makecode.microbit.org/_6KY8EF7CvV1D

Shows how to clean up data into useful range.

But boring!

Neopixels and Flex sensor:
https://makecode.microbit.org/_Kcog2V9WgEA3


Lessons: need to map values to a useful range 
This is where a serial monitor is useful

What do you do with the output
 - log to console...
  - send to app - get app?
   - control device - RGB LED...? 
    - neopixels: https://makecode.microbit.org/_CAWipEfxqb5m

<!-- ### Motors

Can't seem to drive one from the pins
PWM is available on several pins: https://tech.microbit.org/hardware/edgeconnector/

Doesn't work withthe motors I have - but does work with LEDs!
Could try this with an RGB LED...? -->

### Connecting Microbits together
http://www.multiwingspan.co.uk/micro.php?page=bit2bit

## Get input and send it to a phone

Bitty Datalogger app: <https://www.bittysoftware.com/apps/bitty_data_logger.html>


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
* Create a higher fidelity prototype that could be embeded in a device or worn on clothing

Show your research and include reflection on the process, and other resources you have found. 

<!-- 
## Formative Assessment is next week

The deadline for formative assessment is: 10am, Monday 30 March
[Formative assessment details](https://fablabbrighton.github.io/digital-fabrication-module/course-notes-lm225-2020/formative-assessment) -->
