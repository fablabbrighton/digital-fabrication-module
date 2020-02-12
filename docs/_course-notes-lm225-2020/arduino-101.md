---
layout: page
title:  "Arduino for Beginners"
date:   2020-02-12
author: Andrew Sleigh
---

From zero to blinking LEDs with Arduino

<!--more-->

## Aims for class

* A brief intro to Arduino, was it does and how it relates to other technologies that ‘do stuff’
* Get everyone from zero to getting your Arduino hooked up and talking to your computer, and a program running
* A bit of hacking of code that other people have written
* If we have time, we’ll look at how we might build some of the prototypes you want to make



## Microcontrollers and embedded programming

Development boards and microcontrollers
What’s in a microcontroller
How do we access it
What are all the bits on an Arduino



## What is a microcontroller?

Microcontroller vs Microprocessor  
Simpler computer  
Has lots of ‘peripherals’ inside - see block diagram  
Microprocessor is what’s inside your computer - needs lots of external parts to make it work: RAM, GPU, disk, etc.

## What’s inside a microcontroller?
See [Megaprocessor](http://www.megaprocessor.com)

Or look at a datasheet:

![ATtiny-Block-Diagram.png]({{ "/assets/ATtiny-Block-Diagram.png" | relative_url }})

Capabilities:
* Tell time / keep time
* Remember data
* Read analogue signals from the outside world
* Talk to other microcontrollers
* Send and control power out to other devices


## How can we access these capabilities?

![attiny-pinout.png]({{ "/assets/attiny-pinout.png" | relative_url }})


## "Arduino"


1. A board (or family of boards)

2. An IDE

* Text editor
* Console and serial port monitor
* Bundled tools for compiling code and uploading it to the Arduino (avr-gcc)
* Bundled examples, board definitions etc.

3. A library for C/C++

You're writing C code, and taking advantage of *libraries* written to make controlling an Arduino easier:

```
void loop() {                       // Defining a function in C
  digitalWrite(LED_BUILTIN, HIGH);  // Using Arduino library functions 
  delay(2000);                      
  digitalWrite(LED_BUILTIN, LOW);   
  delay(1000);                      
}
```

4. An open source community

Designed for artists and other non-engineers. Newbie-friendly.
Open Source (Eg Creality printer)
Tutorials, answers online: Google first!
Clone boards and compatible tech, e.g. add-on ‘shields’
Variants - eg micro sew-on boards, DIY boards
Pathways to other platforms: ESP8266, Arm, Bela, Pi, Processing


## Getting started

Download, install and verify the Arduino IDE software for your computer:
<https://www.arduino.cc/en/Main/Software>

If you want to use the web editor, you must create an account and install the plugin first:
<https://create.arduino.cc/projecthub/Arduino_Genuino/getting-started-with-arduino-web-editor-on-various-platforms-4b3e4a>

## Hacking code


You don't need to start from scratch!
Everyone learns by hacking other people's code – but credit your sources.
Arduino comes with simple examples for many common tasks (File > Examples)
There are libraries for many more (reading an SD card, playing MP3s, controlling stepper motors)
There are code examples everywhere on the web



### Example sketch: Blink

```
// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(LED_BUILTIN, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);                       // wait for a second
  digitalWrite(LED_BUILTIN, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);                       // wait for a second
}
```
