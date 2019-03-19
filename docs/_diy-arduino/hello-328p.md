---
layout: page
title:  "First working design"
date:   2019-03-19
author: Andrew Sleigh
---

I've arrived at a viable design, based heavily on Daniele Ingrassia's _Satshakit_ board


<!--more-->

## Git repo

Full details for this board, including Eagle files are in the git repo: 
<https://github.com/fablabbrighton/hello328p>


![Hello 328p board]({{ "/assets/hello328p-milledandstuffed.jpg" | relative_url }})

**Hello 328p** is designed to be a 100% Arduino Uno-compatible board, that can be easily fabricated by students in a fablab. It uses the ATmega328P microcontroller and is very heavily based on [Daniele Ingrassia's Satshakit board](https://github.com/satshakit/satshakit), which also serves the same purpose. The main changes to this design are to provide a simpler way to connect things to the board through more convenient headers and labelling on the board itself.

Please read [Daniele's documentation](https://github.com/satshakit/satshakit) for full details on this board. These docs will only address the changes made.

## Background

I have spent a few months exploring different approaches to making my own Arduino-compatible board. My aim is to find (or design myself) a board that can be easily milled and stuffed by students, and then used in their own interactive projects. I also wanted to learn more about Arduino, the ATMega328p and board design in the process. 

After trying many boards is a starting point, I found Daniele's Satshakit design, which was well-documented, simple, and tested in a Fablab. I successfully made and programmed the board, but I found the header arrangement rather unhelpful.

![Programming the satshakit with a FabISP]({{ "/assets/program-satshakit.jpg" | relative_url }})

In this photo, I'm using my FabISP to program a Satshakit. You can see that it involves a lot of jumper wires, and that there is no simple connection between the 3x2 pin ISP header on the programmer, and the relevant pins on the target board. 

The upside of this approach is that the board design is very simple. Almost all the pins from the microcontroller are simply exposed out to pins on headers that surround it. The traces are very straightforward.

However, that pushes some complexity back onto the user, who has to figure out which pins to connect where, when burning the bootloader, or whenever they want to program the board. I think there is a friendlier way to do this, with only a small overhead in complexity of traces. _Hello 328p_ is my attempt at that.

The photo below shows the Hello 328p board being programmed with a FabISP, via one simple ribbon cable. You can also see the handy pads for connecting a power supply with crocodile clips.

![Hello 328p programming]({{ "/assets/programming-hello328p.jpg" | relative_url }})


## Hello 328p header layout

This diagram shows all the headers, and which pins on the chip they are connected to. In addition, pin functions for the FTDI and ISP headers are highlighted in pink, and the Arduino labels for analogue and digital pins are highlighted in yellow.

![Hello 328p pinout]({{ "/assets/hello-328p-pinout-labels.png" | relative_url }})


## Programming the board

Please see the full instructions in the GitHub repo: 
<https://github.com/fablabbrighton/hello328p>

