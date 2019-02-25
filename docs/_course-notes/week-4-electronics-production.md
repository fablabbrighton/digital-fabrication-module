---
layout: page
title:  "Week 4: Electronics production"
date:   2018-12-07
author: Andrew Sleigh
---

Making our first circuit board. 

<!--more-->

## Prep for this week's class

Watch the corresponding Fab Academy lecture. We'll be covering part of this content. 

* Fab Academy lecture notes: <http://academy.cba.mit.edu/classes/electronics_production/index.html>  
* Lecture from 2018 (Fab-20180214D_Lesson04, the second video on the page): [Fab-20180214D_Lesson04 Recordings](http://fab.academany.org/2018/lectures/fab-20180214.html)

If you like, watch this short [YouTube playlist](https://www.youtube.com/watch?v=XdamEhs2RIk&list=PL-xEsC0ZUCUM42QNHaOOdoOwYg0j251dU&index=1) showing the wole milling process. 

## Baseline 

Who has:
* Made something with electronics?
* Used a CNC machine of any kind?

You don’t need to know any electronics this week.

We'll start by producing a board, before we do design - you may not understand what the parts are, or why they are connected this way, we're just learning how to put it together.

----


## How to make a circuit

Just need a way to support and connect all the electrical components:

* Jumper wires and crocodile clips (not useful for any level of complexity)
* Conductive thread sewn into garments (good for components, but not for microcontrollers)
* Copper tape cut with the vinyl cutter, stuck to anything ([giant programmer](http://fab.cba.mit.edu/classes/863.17/CBA/people/seanhickey/weeks/06-large-format-machining/) / [picture]({{ site.baseurl }}/assets/sean-hickey-giant-programmer.png)) 
* Breadboards ([picture]({{ site.baseurl }}/assets/breadboard.jpg)) (unreliable, not scalable, a first step only - even on milled boards, you can edit afterwards)
* Stripboard ([picture]({{ site.baseurl }}/assets/stripboard.jpg)) (like the inside of a breadboard, needs soldering)
* PCBs (printed circuit boards) 


## Making PCBs
Most are made from copper laminated onto a non-conductive substrate, and then copper selectively removed to form traces, pads, vias, etc.

## Etching 
Commercial process, hobbyist/prototyping level 
* Uses nasty chemicals, safe disposal is non-trivial
* **You** must manage the lifecycle

## Milling
How we do it.  
Great for prototyping - every board can be different.  
Not so good for batch production - slower than etching.  
Move a tool bit around removing copper to leave circuit behind.   
[Video series of whole process](https://www.youtube.com/watch?v=XdamEhs2RIk&list=PL-xEsC0ZUCUM42QNHaOOdoOwYg0j251dU&index=1)

### The Milling Machine
[Roland MODELA MDX-50 Benchtop CNC Mill](https://www.rolanddga.com/products/3d/mdx-50-benchtop-cnc-mill)

Accuracy:
* positioning (< 1/1000”)
* tolerances (approx. 1/1000)
* e.g. bit size for traces: 0.3mm diameter

### Tools
* Cutting outline of board (1mm diameter)
* Cutting traces (0.3 or 0.4mm diameter)

Tools are a consumable - maybe make 20 boards/tool if used properly.  
Hard but brittle - don’t drop or knock.


### Materials
FR1 - paper-reinforced (not FR4, which is glass-based)


### Scaling up
The desktop mill is good for 1-10 boards.  
What if you want to make loads of boards for an art project or small product run?  

* Board houses can mill boards, but also stuff, or even source components, and fabricate.  
* Or go to Shenzhen (or go through an online intermediary). 

## Process

See our [Fab Academy docs](https://docs.google.com/document/d/14R-S-bQIisVIhJUZ70ZwEbi74LaQbHa-e2ixB39OMN8/edit#heading=h.9uukav7e0zv2)

### 1. Starting point: a PNG file of the circuit you want to mill

![<#alt_text#>]({{ "/assets/hello.ISP.44.board-traces-stuffed.png" | relative_url }})


### 2. Generate a tool path (CAD to CAM)

CAM software:  
* [Fab Modules](http://fabmodules.org). Web-based, so use it on any computer


#### Fab Modules settings

**Input format**

Choose your png traces file.

![pcb-mill-workflow-1.png]({{ "/assets/pcb-mill-workflow-1.png" | relative_url }})


Traces are white, material to be removed is black - may need to invert your png.  
Check resolution is the same as your png file.


![pcb-mill-workflow-2.png]({{ "/assets/pcb-mill-workflow-2.png" | relative_url }})

**Output format**  
Roland mill (.rml)

**Process**  
PCB traces (1/64”) or PCB outline  (1/32”)


**Output**  
```
Machine: MDX-40   

speed (mm/s):   4  

x0 (mm):  0  
y0 (mm):   0  
z0 (mm): 0  

zjog (mm):  2  (a safe height above board)

xhome (mm):  0  
yhome (mm):  0  
zhome (mm):  0  

cut depth (mm): 0.1mm (can adjust this)   

tool diameter (mm): 0.4 or 0.3 (Make sure it’s the same as the tool!)

number of offsets (-1 to fill):  
1 to verify.  
2 is enough clear space to solder.  
4 makes life a bit easier.  
-1 removes all non-circuit material. Looks nice, but takes ages.
```

**Calculate**  
Hit calculate to see a preview of tool path.  

![pcb-mill-workflow-3.png]({{ "/assets/pcb-mill-workflow-3.png" | relative_url }})

You will probably need to go back several steps in the workflow here to address problems.

Typical problems:
* Traces and pads merging 
* Traces running underneath components

Fixes:
* Move components in the board layout 
* Reduce pad sizes (don’t change pitch!)
* Use a different milling bit
* Lie to the machine about which milling bit you're using

**Save**  
Once it’s working, hit save to generate RML file.
(A similar process to generate RML file for cutting outline.)
Save the rml file somewhere you can find it.
Rml looks like this; very simple instructions:

```
PA;PA;VS4;!VZ4;!PZ0,200;!MC1;
PU350,4075;
Z350,4075,-10;
Z304,4077,-10;
Z276,4097,-10;
Z262,4129,-10;
Z264,4167,-10;
Z282,4193,-10;
Z306,4207,-10;
Z336,4211,-10;
...
```

#### 3. Set up the milling machine ([docs](https://docs.google.com/document/d/14R-S-bQIisVIhJUZ70ZwEbi74LaQbHa-e2ixB39OMN8/edit#))

**Prepare bed**

* Sacrifical material  
* Must be flat and clean  

**Attach board to bed**

* Double-sided tape
* Got to get board flat - secure taping, and remove warps

**Select tool**

* Know what tool is in what cartridge (1-6). 


**Set x, y, z zero**
* Set x and y home (allow some space, but make your your design fits on your board)
* Lower tool to surface, set z0. Always spin the tool when setting z


#### 4. Back to the computer: Send your rml file to the mill.

Open your rml file in VPanel.

![vpanel.png]({{ "/assets/vpanel.png" | relative_url }})

When you hit output, the machine will start milling. Stand by in case something goes wrong.


#### 5. Mill it

Keep an eye on things!


<video src="{{ "/assets/video/milling-mistake.m4v" | relative_url }}" controls preload></video>

#### 6. Cut outline

* Similar process to cut outline. See [docs](https://docs.google.com/document/d/14R-S-bQIisVIhJUZ70ZwEbi74LaQbHa-e2ixB39OMN8/edit#) for more detail.


#### 7. Clean and check board

* Deburr board with abrasive sponge
* Clean skin oils off copper
* Verify your traces look correct (clean, not shorting, right size)



### Design rules
Consider the machine, tools, materials and process when designing your circuit (next week).

* Machine has a level of stability ( = accuracy)
* Tools are round (how to cut a right angle?)
* Tools have a thickness (how close can traces be?)
	* Neil: 15mil (mil = 1/1000 of an inch, not millimetre - see Eagle)
* Some tools are conical, so diameter varies (what if your board or bed isn’t flat?)

----

Now we have the traces on a board. What next?


## Components


[Surface-mount (SMD)](https://octopart.com/attiny44a-ssu-microchip-77762206?r=sp&s=cUQgI0hKTAescWgW-TJY5A) - [picture]({{ site.baseurl }}/assets/smd.png)

[Through-hole](https://octopart.com/attiny44-20pu-microchip-77762184?r=sp&s=CoYFhS4PRYWqjK8yBgiHYw) - [picture]({{ site.baseurl }}/assets/pth.png)  
Often used by hobbyists - not us. Becoming obsolete.

[Chip scale](https://octopart.com/attiny44a-mu-microchip-77762199?r=sp&s=IoZaPY0RRHqdTN2UABj1MA) - [picture]({{ site.baseurl }}/assets/chipscale.png)


See the [components guide for the FabTinyISP Programmer](({{ site.baseurl }}guide-stuff-isp))


## Soldering

Guide: [Adafruit Guide To Excellent Soldering](https://learn.adafruit.com/adafruit-guide-excellent-soldering/surface-mount)

Videos:  
[SMD Soldering - the easy way - YouTube](https://www.youtube.com/watch?v=wEBrvfWwzuQ) (Arthur Guy)  
[EEVblog #186 - Soldering Tutorial Part 3 - Surface Mount](https://www.youtube.com/watch?v=b9FC9fAlfQE) (enthusiastic Aussie, unavoidable)
[Basic Soldering Lesson 1 - "Solder & Flux"](https://www.youtube.com/watch?v=vIT4ra6Mo0s&index=1&list=PL926EC0F1F93C1837) (excellent retro series, especially this video on materials: copper, solder and flux and how they work: e.g. [clean copper]({{ site.baseurl }}/assets/clean-copper.png), 
[thermal mass]({{ site.baseurl }}/assets/thermal-mass.png)) 

### Remember:

* Clean your board to remove copper oxide and finger oils
* Keep soldering iron tip shiny and clean
  * Switch the iron off when you're not using it
  * Don't be tempted to use too high a temperature (that is not why your solder isn't melting)
* Melting solder wets the joints
* Heat both parts of the joint with the iron
* Feed in small amount of solder - helps conduct heat
* Wait – learn to see the signs of a good flow and joint forming
* Once parts are at the right temperature, more solder will flow up and down parts
* Wait, then remove iron
* Check your work – you want shiny, smooth joints


### Recognising a bad joint
[Common Soldering Problems - Adafruit Guide To Excellent Soldering](https://learn.adafruit.com/adafruit-guide-excellent-soldering/common-problems)

[Picture]({{ site.baseurl }}/assets/solder-joints.jpg)

### Techniques
#### Holding the board
* Tape
* Vice

#### Holding the part
* Tacking 
* Note orientation of chips, capacitors, diodes, etc.
* Order of stuffing - inside out

#### Desoldering
* Braid - tin the braid first to help heat flow
* Pump
* Hot air gun - use directional tip (plus tweezers and gravity). Clean up with braid afterwards.

### Safety
Fumes  - an issue if you’re soldering for several hours  
Leaded solder - Wash your hands!


---


## Assignment

Mill and stuff an ISP programmer. Follow this design and instructions: [Building the FabTinyISP](http://fab.cba.mit.edu/classes/863.16/doc/projects/ftsmin/index.html)  
To really verify that is works, load the board with the programming software.  
(What is an ISP programmer, and why do I need one?)


<!-- 
<span class="wip">WIP</span> Not sure which is best here: to make a progammer (1) or a simple microcontroller board (2).
 -->

<!-- (1)  Mill and stuff a board a DIY version of a [commercial Atmel programmer](https://www.digikey.com/product-detail/en/microchip-technology/ATATMEL-ICE-BASIC/ATATMEL-ICE-BASIC-ND)

* Brian’s: [Building the FabTinyISP](http://fab.cba.mit.edu/classes/863.16/doc/projects/ftsmin/index.html) Tiny45-->
<!-- * Ali’s: [FabISP_Demystified](http://fab.cba.mit.edu/classes/863.16/doc/tutorials/FabISP/FabISP_Demystified.html) TIny44 -->

<!-- 

<span class="wip">WIP</span>: I suggest we make the ATtiny45-based board (look like a USB key)
* Don't need a resonator, which is difficult to solder
* Don't need a USB port, also difficult to solder
* Only 1 connection to break after programming

 -->




<!-- CrossPack is a development environment for Atmel’s AVR® microcontrollers running on Apple’s Mac OS X, similar to AVR Studio on Windows. It consists of the GNU compiler suite, a C library for the AVR, the AVRDUDE uploader and several other useful tools. -->

<!-- 

USB-3
There have been reports of problems with certain USB-3 ports due to the stricter timing USB-3 requires, from what I've understood all FabISPs seem to be suffering from this. The workaround is to try another USB port or even an USB-2 (or lower) hub. As I don't have any USB-3 ports (yet), I cannot really test this myself.
 -->

<!-- 
Or

(2) Mill and stuff the Hello World board (then next week we can modify it)
 -->


### What do I need to do to pass?

Mill and stuff a board that passes a visual inspection (good traces, viable solder joints, correct components in the right places).

(If there isn't enough time for everyone to mill a board, we may do this in batches.)

**Document all your work on your student blog, with photos and videos to show what you did, what went wrong, and how you fixed it. Cite external sources where you have used someone else's work.**


### Extra credit

1. Mill a board and teach someone else how to operate the machine
2. Test the board you make with oscilloscope or the multimeter and document what you find
3. Test that the board really works by verifying it does what it’s supposed to do (i.e. accept a program loaded onto it)

---

### For next week

You will need access to a functioning programmer for next week.  
Ideally, it should be one that you have made.

- - - -

## Materials we need this week

<!-- 
Plan A: <span class="wip">WIP</span>

* A board design
* USB extension cables (if we’re using USB key-style programmer boards)
* Components for the programmer
* Sheet with a diagram of each component 
* FR1 for milling



Plan B:

* Some pre-milled boards
* Working programmers (if we’re not making them)
 -->
 
 * Cutting files for programmer: <http://fab.cba.mit.edu/classes/863.16/doc/projects/ftsmin/index.html>
 * FR1 for milling
 * Some pre-milled boards <span class="wip">WIP: make these</span>
 * USB extension cables (for USB key-style programmer boards)
 * Components:
    * 1x ATtiny45 or ATtiny85
    * 2x 1kΩ resistors
    * 2x 499Ω resistors
    * 2x 49Ω resistors
    * 2x 3.3v zener diodes
    * 1x red LED
    * 1x green LED
    * 1x 100nF capacitor
    * 1x 2x3 pin header

 
---

### Failsafe for next week

Make some working programmers so students can use them to program their boards

