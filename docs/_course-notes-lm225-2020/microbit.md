---
layout: page
title:  "Programming interactivity with the BBC Microbit"
date:   2020-01-03
author: Andrew Sleigh
---

An introduction to making interactive devices

<!--more-->

## Prep for this week's class

* Watch the Microbit intro videos: <https://microbit.org/guide/quick/>
* Read this introduction: <https://learn.adafruit.com/bbc-micro-bit-lesson-number-0?view=all>
* Familiarise yourself with the online programming environment: <https://makecode.microbit.org>

## Baseline 

We assume no prior knowledge of microconroller, the MIcrobit, or programming. However, you will find it **much** easier if you have looked at the materials in the Prep section, and played around with the [online programming environment](https://makecode.microbit.org).


## Making interactive devices

"Making stuff do stuff"

Should go into big picture stuff here, cos assignment is simple

Spectrum:
Learning - Prototyping – Small-scale manufacturing – Large scale

Microbit
Arduino
AVRs
Commercial ICs
Blob ICs

## "Embedded programming" and microcontrollers

### What is a microcontroller?

Microcontroller vs Microprocessor  
Simpler computer  
Has lots of ‘peripherals’ inside - see block diagram  
Microprocessor is what’s inside your computer - needs lots of external parts to make it work: RAM, GPU, disk, etc.

#### What’s inside a microcontroller?
See [Megaprocessor](http://www.megaprocessor.com)

Or look at a datasheet:

![ATtiny-Block-Diagram.png]({{ "/assets/ATtiny-Block-Diagram.png" | relative_url }})

Capabilities:
* Tell time / keep time
* Remember data
* Read analogue signals from the outside world
* Talk to other microcontrollers
* Send and control power out to other devices


### How can we access these capabilities?

![attiny-pinout.png]({{ "/assets/attiny-pinout.png" | relative_url }})



## The Microbit

Tour of the hardware:<https://learn.adafruit.com/bbc-micro-bit-lesson-number-0?view=all#take-a-tour>



## Writing programs for the Microbit



[online programming environment](https://makecode.microbit.org).
https://python.microbit.org/v/2.0

Tour of the interface

Basic blocks

`on start`
`forever`

My buton test: https://makecode.microbit.org/_RL0igj2Hiivk


Intro: <https://learn.adafruit.com/bbc-micro-bit-lesson-number-0?view=all#lets-code>

[Mobile or Tablet](https://microbit.org/guide/mobile/)

Uploading programs via USB or Bluetooth

Good USB data cable


Things you can do

## Onboard I/O: Read an onboard sensor and show a response on the LED matrix

Buttons
Accelermeter
...

## Coding 

Environmet
Phone option

DOwnloading programs - stat withdrawgin on matrix
Then do buttons


## Outboard I/O: Connect a sensor or control and control an output

Environmental sensor

### What you'll need

Microbit
USB Cable
Breadboard
Breadboard adapter

External input: sensor, potentiometer, button
External output: LED, OLED screen, LCD Screen, motor, buzzer, relay, servo


Concepts:

Understanding what's significant and what isn't on the breadboard
Internal wiring

Maybe start with just a breadboard circuit...

How to plug parts in
esp microbt header - over midle secion - so pins aren't connected
Demo with multimeter

Puting values into variables so you can use them elsewhere

Analog vs digital iputs and outputs
Possible values
Calibrating sensor - e.g. for wearables

Logic loops
Simple if else
Adding more tests - how tests can fail



The forever loop vs on start

sending digital value 1 = 3V to LED

Basic LED circuit: Light an LED with just 3V and GND pins!


Note pinout diagram (of Microbit and ofBreadboad connector)
* Note some pins interfere with LED Matrix
* back pins of connector do not go sequentially!

https://microbit.org/guide/hardware/pins/
> pin 3 is shared with some of the LEDs on the screen of the BBC micro:bit, so if you are using the screen to scroll messages, you can’t use this pin as well.


## Ideas


### Onboard IO

Compass to PWM - not very good!
https://makecode.microbit.org/_hAdVJ7he4fHA


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

Shows how to clean up data into useful range
But boring!


What do you do with the output
 - log to console...
  - send to app - get app?
   - control device - RGB LED...? 
    - neopixels: https://makecode.microbit.org/_CAWipEfxqb5m

### Motors

Can't seem to drive one from the pins
PWM is available on several pins: https://tech.microbit.org/hardware/edgeconnector/

Doesn't work withthe motors I have - but does work with LEDs!
Could try this with an RGB LED...?

### Connecting Microbits together
http://www.multiwingspan.co.uk/micro.php?page=bit2bit

## Debugging: sending data to the serial console

https://makecode.microbit.org/device/serial


Find out the port your Microbit is on (on Mac):
`ls /dev/cu.*`

Result, something like this:
`/dev/cu.Bluetooth-Incoming-Port  /dev/cu.usbmodem14202`

Pick one that looks likely - not the Bluetooth port in this case.

Start a serial connection on that port, with a specified baud rate
`screen /dev/cu.usbmodem14202 115200`

To exit `Ctrl-A` then `Ctrl-D`


## Netwoked Microbits


## Get input and send it to a phone







## Assignment

Should get them to play as far as they can go.
If we get far, we can do more arduino next week


See: 





### What do I need to do to pass? (40%)

Write a program using the code blocks editor that uses the buttons or sensors on the Microbit to display somethign on the LED display.

Experiment with the different sensors. What kinds of data can you get out of them? How are they imperfect? (How can they be misleading, or unreliable, and what can you do to 


Document all your work on your student blog, with photos and videos to show what you did, what went wrong, and how you fixed it. 

Cite external sources where you have used someone else's work.

### Extra credit (50-100%)

Write several programs to demonstrate how the different sensors work.

Explore the different blocks availble in the code editor. Describe what they do, and how you could use them. 

Try to implement the same program using the MIcroPython editor. What are the differences?
Can you make the microbit communicate with your computer - e.g. to send messages back.
Can you include logic in the program to make it communicate in a more 'human' way?

Try to make a game that ues the buttons or sensors for input, where the player has to respond to images on the LED display (e.g. Simon Says, Tetris, a driving game).

---

## Further reading / watching

* <https://learn.adafruit.com/micro-bit-lesson-1-using-the-built-in-sensors>
* <https://learn.adafruit.com/micro-bit-lesson-2-controlling-leds-on-breadboard>
* <https://learn.adafruit.com/micro-bit-lesson-3-neopixels-with-micro-bit>
* <https://learn.adafruit.com/micro-bit-lesson-4-sensing-light-and-temperature>



## For next week

Do some research about basic electronics:

* How circuits work
* Inputs and Outputs

