---
layout: page
title:  "3D Fabrication: Milling Machine"
date:   2020-01-02
author: Andrew Sleigh
---

Part 1: Introducing computer-controlled machining.  
Part 2: Introducing moulding and casting

<!--more-->



## Computer-controlled machining
[**computer-controlled machining**](http://academy.cba.mit.edu/classes/computer_machining/index.html "computer controlled machining")

## Hardware

[Roland MX-50](https://www.rolanddga.com/products/3d/mdx-50-benchtop-cnc-mill) milling machine, 400x350x150mm (XYZ)

:thought_balloon: Explore the machine

### Tooling

:thought_balloon: Look at some bits

- [milling bit types](http://mindworks.shoutwiki.com/wiki/Cutter_Types_(Mill)): ball-nose, flat-end mills
- [number of flutes](http://www.cs.cmu.edu/~rapidproto/students.03/zdb/project2/CNCflutes.htm)
- [coatings, centre-cutting and general cutter guide](https://www.cnccookbook.com/cnc-end-mill-guide/)
- [up/down cut](https://www.guhdo.com/blog/up-vs-down-shear-router-bits/)




## Software

### CAM tools

*   SRP player (Roland MX-50)
*   [Solidworks CAM](https://www.youtube.com/watch?v=pPxH-JGTCK4)
*   [SolidCAM](https://www.solidcam.com/professor/solidcam-modules-overview/) , [demo](https://youtu.be/di-VxpxAUGQ) , [tutorials](https://www.solidcam.com/professor/solidcam-jumpstart/),  [machine building](https://youtu.be/R3pW8RenKZk) (see simulation below)
*   [Fusion 360](https://www.autodesk.com/products/fusion-360/blog/getting-started-introduction-to-cam-and-toolpaths/)
*   [fabmodules](http://fabmodules.org), and [here's the documentation](https://github.com/FabModules/fabmodules-html5)
*   [fabmods](http://mods.cba.mit.edu/), and [here's the documentation](https://gitlab.cba.mit.edu/pub/mods)

### Software to run CNC machines

- [GRBL (standard)](https://github.com/gnea/grbl)
- [GRBLcontrol - PC/linux only (runs the small 1610 machine)](https://github.com/trasz/grblControl)
- [swift cut (plasma cutter)](https://swift-cut.com/)
- [VPanel (Roland MX-50 in fablab)](http://support.rolanddga.com/Docs/Documents/departments/Technical%20Services/Downloads/MDX-50_INS_EN_R2.pdf)
- [Winmax (Herco VM10UI in Adam's workshop)](http://www.hurco.com/en-us/cnc-machine-tools/our-control/pages/winmax.aspx)
- [VCarvePro (AXYZ at Grand Parade)](https://www.vectric.com/products/vcarve-pro)
- [Marlin](http://marlinfw.org/)
- [Mach3](https://www.machsupport.com/software/mach3/)


## Workflow for CNC machining

* CAD: Design model, export as STL
* CAM: Generate toolpath + export G-code 
* Load into machine software 
* Set Machine origin (XYZ0) values and verify bits
* Run job (cut fresh air)
* Run job (with stock)


## Terminology

### Milling


- [speeds n feeds](https://en.wikipedia.org/wiki/Speeds_and_feeds)

    * Spindle speed (speed of rotation)
    * Feed rate (movement of bit acros the workpiece)

- [chip load: ~ 0.001-0.010"](https://www.cutter-shop.com/information/chip-load-chart.html)
- feed rate (inches per minute) / (RPM x number of flutes) 
- cut depth: ~ tool diameter
- step-over: ~ tool diameter/2

### Molding and casting

* 'Pattern' or 'Model' or 'Mould Tool' https://en.wikipedia.org/wiki/Pattern_(casting)
* 'Mould' https://en.wikipedia.org/wiki/Molding_(process)
* 'Casting' from the mould https://en.wikipedia.org/wiki/Casting

## Design rules and considerations

Axes

## rules for making simple mould tools
1. Vertical walls should have [draft angles](https://www.dynacast.com/stuff/contentmgr/files/0/97f5240f1f1a61eac4d6f431cbd0b2d4/files/diecasting_design_tips_01.jpg)
2. There should be no [undercuts](http://www.acomold.com/image/molding-undercuts.jpg), you should be able to cut it all from above.


Bit size and shape: Diameter, spindle length, shoulder

Material qualities: Fast or slow spindle speed, feedrate, fragility 

Strategies
Model placement
Draft angles
Minimum feature size
Adding fragile parts manually (e.g. using straws, bolts, sheets)



Pour holes 
Time - quicker to make a ox on the laser cutter, than to mill it from wax


Size of wax block - confirm how margins work - try switching them off entirely



Check tools in magazine 

Set machine origin first

Use Fablab manual as guide - dont need to write all this stuff


Cut air first!!!

Understandig margins - the job will be centered in the workpiece

So a 4x4cm job in a workpiece of 5x5cm will have an extra 0.5cm boder all round


https://docs.google.com/document/d/14R-S-bQIisVIhJUZ70ZwEbi74LaQbHa-e2ixB39OMN8/edit#heading=h.9uukav7e0zv2





### [Introducing moulding and tools](https://en.wikipedia.org/wiki/Injection_moulding)
- [injection moulding: sprue, gate, runner, vent, parting line, flashing](http://custom-injection-molding.net/wp-content/uploads/2014/03/D1-03.gif)
- [+'ve solid tool > -'ve flexible tool > +'ve solid part]({{ site.baseurl }}/assets/positive-negative-positive-moulding.JPG)
- [-'ve solid tool > +'ve flexible part]({{ site.baseurl }}/assets/pu-copper-ducks-in-mould.jpg)
- [mould tools with registration](http://academy.cba.mit.edu/classes/molding_casting/tippy.png)
- [flexible parts](http://fab.cba.mit.edu/classes/863.13/people/crreed/weekly/week6.html)

### process for making mould tools
- mixing: by weight or volume
- pouring: starting, filling, vent location
- bubbles: stirring, pouring, vibrating, painting, vacuum, pressure, time
- curing: polymerization, cross-linking, hydration, endothermic, exothermic
- demolding: draft angle, release agents (dilute dish soap, vaseline, talc, other), deformation

### other notes
- storage and shelf life
- safety: read the SDS!, ventilation, personal protective equipment (PPE), disposal


## Assignment

Create a 40 x 40 x 5 mini tile model in Fusion 360.
Mill it out of a block of wax.




### What do I need to do to pass?
- create the cad model of your tile and generate the toolpath and document this on your blog, ideally including an animation of the toolpath (like the one provided on the guide). 

Demonstrate safe and tidy use of the CNC mill, and moulding and casting materials.

Document all your work on your student blog, with photos and videos to show what you did, what went wrong, and how you fixed it. Cite external sources where you have used someone else's work.


## Extra credit

Create a silicon mould and cast the finished part from chocolate or plaster of paris.

Try milling form another material, or experiment with adding parts to your mould tool manually. 

## Resources / find out more

* Fab Academy lecture notes (computer-controlled machining): <http://academy.cba.mit.edu/classes/computer_machining/index.html>  
* Fab Academy lecture notes (moulding&casting): <http://academy.cba.mit.edu/classes/molding_casting/index.html>  
* [Lecture from 2018 - computer-controlled machining](http://fab.academany.org/2018/lectures/fab-20180307.html)
* [Lecture from 2018 - moulding&casting](http://fab.academany.org/2018/lectures/fab-20180321.html)

* [guide to CNC machining a mould tool using the 1610 mini CNC machine](https://fablabbrighton.github.io/digital-fabrication-module/guides/guide-milling-mould-tool.html)
* [CNC design guide](https://www.3dhubs.com/knowledge-base/how-design-parts-cnc-machining) 
* [Make: Design for CNC book](https://www.amazon.co.uk/Make-Practical-Techniques-CNC-routed-Furniture/dp/1457187426)