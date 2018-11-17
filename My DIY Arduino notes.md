---
layout: page
title: My DIY Arduino notes
permalink: /diy-arduino/
---


# My DIY Arduino notes

## Why do it?
I want to design a simple board that beginning students will be able to ill and stuff themselves, and which they can incorporate into their own projects, i.e:
* A step up from the ATTiny boards we make to do simple blinking LED and I2C tests in Fab Academy
* A step down from the Leonardo-style boards we make, which use more complex chips, in very small package sizes 

## Who to learn from?
* Arduino themselves have instructions for a breadboard version, with each component explained: 
	* [Arduino - Setting up an Arduino on a breadboard](https://www.arduino.cc/en/Main/Standalone)
	* [Setting up an Arduino on a breadboard](bear://x-callback-url/open-note?id=58B37E4D-8F1B-4471-888A-53F32C3708F7-1184-00001C1B546B4BB3) – Itself derived from: [ITP Arduino on a breadboard](https://itp.nyu.edu/archive/physcomp-spring2014/Tutorials/ArduinoBreadboard)
* Shrimping.it have a very simple breadboard version, but not much documentation
* Adafruit Feather board is a commercial/OSHW clone of the Arduino board with freely available design files
* Adafruit also make a [Boarduino](https://learn.adafruit.com/boarduino-kits/overview), designed to plug into a breadboard
* Modern Device also have a “Really Bare Bones Board”: [RBBB (Really Bare Bones Board) | Modern Device](https://moderndevice.com/product/rbbb-kit/)

* This is a [great series](https://rheingoldheavy.com/category/education/fundamentals/arduino-from-scratch-series/) unpicking the Arduino and rebuilding a clone


## Initial questions
### Which chip to use
* Which chips are in the standard Fablab inventory
* Bigger packages are easy to solder
* DIP packages can be seated in sockets which allows for more error when soldering
* How many pins, and does it matter (some packages have 32 pins and some 28)

### Which components/systems are necessary?
* Power regulation
* USB power
* Programmer?
* Status LED
* Reset button
* … etc…
* 


## Understanding the Arduino breadboard systems
### Power supply
They set up a 5V power supply using a 7805 power regulator. 
I might be able to get away without this. 
**But how will my board be powered?** 
	* A power-only USB socket (could be confusing)
	* A standard barrel jack (are these in the inventory)

See [this note on polarity protection](https://rheingoldheavy.com/arduino-from-scratch-part-2-voltage-regulator-subsystem/):
> Over on the left, is a component called “Power Supply” with three pins. That’s the barrel jack you’d plug the wall wart into.  
> Moving towards the right, there’s a diode, D1, which acts as a reverse voltage protection diode. Wall warts come in two varieties, because God hates us and wants us to blow up our electronics: positive voltage on the outside of the plug and ground in the middle, or ground on the outside of the plug and positive voltage in the middle. I’ll need to confirm it by looking at the datasheet for the barrel jack, but I suspect this is designed to accept a plug with voltage in the middle. If you connect the wrong type, the reverse voltage protection diode will prevent electricity from conducting in the wrong direction, saving your Uno from blowing up (to a certain extent). The designation “M7” on the schematic means it’s a pretty standard 1N4007 rectifier diode, just in a surface mount package.  

[This page](https://rheingoldheavy.com/arduino-from-scratch-part-4-voltage-conflict-management/)	 has more on protecting the board (and any host computer) when it is connected up to multiple power sources (such as USB and power in through  a barrel jack

### Reset
Reset is Pin 1.
Includes “a 10k ohm pullup resistor to +5V from the RESET pin in order to prevent the chip from resetting itself during normal operation.”
Also wire this pin to a momentary switch.
Other side of this switch goes to GND as well.
> Add the small tactile switch so that you can reset the Arduino whenever we’d like and prepare the chip for uploading a new program. A quick momentary press of this switch will reset the chip when needed.   

More on reset here: [Arduino from Scratch Part 11 - ATMEGA328P DTR and ResetRheingold Heavy](https://rheingoldheavy.com/arduino-from-scratch-part-11-atmega328p-dtr-and-reset/):
> When the 328P on your Arduino gets reset, the bootloader (currently Optiboot, I believe) checks to see if there is a new program waiting to be installed by checking if anything is waiting on the serial line. If a new program is there, the bootloader overwrites the existing sketch with the new sketch and hands control over to it. If no program is waiting, the bootloader drops off and allows the serial connection to run as normal.  


### Clock
“Add a 16 MHz external clock between pin 9 and 10, and add two 22 pF capacitors running to ground from each of those pins.“

Note: the [Adafruit board uses an 8MHz crystal](https://learn.adafruit.com/adafruit-feather-328p-atmega328-atmega328p/overview):
> At the Feather 328P’s heart is at ATmega328P clocked at 8 MHz and at 3.3V logic  

Loads on crystals here: [Arduino from Scratch Part 9: 16MHz Crystal OscillatorRheingold Heavy](https://rheingoldheavy.com/arduino-from-scratch-part-9-16mhz-crystal-oscillator/)
(This is for the ATMEGA16U2 chip on the Arduino board)

### Status LED
(Used as well for running a simple Blink program)
Note for later (when I know what chip I’m using):
> The blink_led program blinks pin 13. Pin 13 on the Arduino is NOT the AVR ATMEGA8-16PU/ATMEGA168-16PU pin 13. It is actually pin 19 on the Atmega chip.  
* Pin 19 to LED+ (anode)
* LED- (cathode) to 220Ohm resistor
* 220Ohm resistor to GND

### Other pinouts from the Atmega328
* Pin 7 - Vcc - Digital Supply Voltage
* Pin 8 - GND
* Pin 22 - GND
* Pin 21 - AREF - Analog reference pin for ADC
* Pin 20 - AVcc - Supply voltage for the ADC converter. Needs to be connected to power if ADC isn’t being used and to power via a low-pass filter if it is (a low pass filter is a circuit that reduces noise from the power source. This example isn’t using one)

This is all you need if you can program your chip elsewhere (this could actually be an option for us, especially if we used DIP packages in sockets, which could be programmed mounted to commercial Arduino boards.)

### USB to Serial
They use a [SparkFun USB to Serial Breakout - FT232RL](https://www.sparkfun.com/products/12731). This breakout board provides a USB to serial UART interface.
The ShrimpingIt board uses a [CP2102 USB to UART Module](http://start.shrimping.it/kit/cp2102.html)
Adafruit use a [SiLabs CP2104](https://learn.adafruit.com/adafruit-feather-328p-atmega328-atmega328p/overview)

#### What is UART?
See [Basics of UART Communication](http://www.circuitbasics.com/basics-uart-communication/)
> UART stands for Universal Asynchronous Receiver/Transmitter. It’s not a communication protocol like SPI and I2C, but a physical circuit in a microcontroller, or a stand-alone IC. A UART’s main purpose is to transmit and receive serial data.  

### Bootloader

**I don’t really understand what this means**
From the [Arduino page](https://www.arduino.cc/en/Main/Standalone):
> Bootloading your Atmega Chips  
> There are several options for bootloading your Atmega chips, a few of which are covered in this tutorial. If you wish to bootload your Atmega chips using your breadboard, an additional part will make your life much easier but is not necessary. AVR Programming Adapter from Sparkfun, SKU.  [BOB-08508](http://www.sparkfun.com/commerce/product_info.php?products_id=8508)   
Also:
> But wait, there’s another step right? If you pulled your Atmega chip out of your Arduino, it has most likely been programed several times by yourself and so it definitely has been bootloaded, so you won’t need to move any further in this tutorial.  
> However, if you purchased some extra Atmega328 or Atmega168 chips from an online store they will have NOT been bootloaded with the Arduino bootloader (with the exception of  [Adafruit Industries](http://www.adafruit.com/index.php?main_page=product_info&cPath=17&products_id=56) ). What does this mean? You won’t be able to program your chips using the USB to serial breakout board and the Arduino software. So, in order to make your new chips useful for Arduino you MUST bootload them and MUST check out step 4.  

#### [What’s a bootloader?](https://www.arduino.cc/en/Hacking/Bootloader?from=Tutorial.Bootloader)
> Microcontrollers are usually programmed through a  [programmer](https://www.arduino.cc/en/Hacking/Programmer)  unless you have a piece of firmware in your microcontroller that allows installing new firmware without the need of an external programmer. This is called a bootloader.  

Lots more useful info on this page about how bootloaders work.

An alternative is to use an [external programmer](https://www.arduino.cc/en/Hacking/Programmer):

**Burning sketches to the Arduino board with an external programmer**
If you have an external programmer (e.g. an AVR-ISP, STK500, or  [parallel programmer](https://www.arduino.cc/en/Hacking/ParallelProgrammer) ), you can burn sketches to the Arduino board without using the bootloader. This allows you to use the full program space (flash) of the chip on the Arduino board. So with an ATmega168, you’ll get 16 KB instead of 14 (on an ATmega8 you’ll get 8 KB instead of 7). It also avoids the bootloader delay when you power or reset your board. However you must have in mind that the Upload Using Programmer procedure doesn’t burn fuses so, if you have a fresh factory micro-controller you have to burn the boot-loader first in order to have a properly working device.

### Power protection for a host computer
Assuming you plug this into a USB port on a computer via some kind of USB socket, do we need to protect that computer from something nasty coming back from the board (perhaps due to bad stuffing or design)
[Build an Arduino Uno R3 From Scratch Part 1Rheingold Heavy](https://rheingoldheavy.com/build-an-arduino-uno-from-scratch-part-1/)
> PTC Resettable Fuses  
> There are a pair of resettable fuses on the schematic, but they have a semi-unusual symbol that you might not run into very often… sort of a box with a slash through it. Those are the cool little components that break the circuit whenever you inadvertently short circuit something and threaten to fry your computer over the USB cable.  

## Parts

### Chip
The [Fablab inventory](https://docs.google.com/spreadsheets/d/1U-jcBWOJEjBT5A0N84IUubtcHKMEMtndQPLCkZCkVsU/pub?single=true&gid=0&output=html) recommends
* ATMEGA328P-AU-ND	IC MCU 8BIT 32KB FLASH 32TQFP

From reading [threads on the Arduino forum](https://www.google.co.uk/search?q=atmega328+32+or+28+pins+site:forum.arduino.cc&client=safari&hl=en-gb&prmd=sivn&sa=X&ved=2ahUKEwjLptOMj9feAhXML8AKHZ3vBqoQrQIoBDALegQICBAI&biw=414&bih=833), I think it would be best to stick to the component used on the original Arduino (perhaps in a different package shape)


## Board design considerations

### Header pins

From [Arduino from Scratch Part 15 - Design RequirementsRheingold Heavy](https://rheingoldheavy.com/arduino-from-scratch-part-15-design-requirements/):

> The shape of the female pin header is well documented in it’s strangeness. The extra spacing on the SPI side of the board preventing a straight run of headers, but also working now in a retroactive-continuity way to ensure things don’t get plugged in backwards. I think it’s important to preserve this pattern to allow full compatibility with any Arduino shield a user might want to use.  
> ![](My%20DIY%20Arduino%20notes/ArduinoUno_pin_header_spacing.png)  
I agree it makes sense to preserve the main pin header placement if possible. 
Or else do it very differently, to optimise for another use, for example putting all the SPI pins in one place, all the analogue pins in one place, etc.

### Power supply
This will not be used in production, so we can assume it will always be powered by USB?
Or if it is to be wearable, perhaps by battery? (If so, is that a 9V supply?)
If there is more than one source (and maybe even if there is only one, we need to manage power in the event that more than one supply is connected at once.

The RBBB has both a barrel jack and can take power over the programming pins via a [FTDI RS232 to TTL cable](https://www.ftdichip.com/Support/Documents/DataSheets/Cables/DS_TTL-232R_CABLES.pdf) like [this one from Adafruit](https://www.adafruit.com/product/70)
![](My%20DIY%20Arduino%20notes/70-03.jpg)


Possibly also with a standard USB cable and a FTDI breakout board like this: 
![](My%20DIY%20Arduino%20notes/s-l300.jpg)


#Digital Fabrication Module/DIY Arduino#