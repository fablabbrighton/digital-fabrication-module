---
layout: page
title:  "3D Fabrication: Milling, Moulding and Casting"
date:   2020-01-02
author: Andrew Sleigh
---

Part 1: Introducing computer-controlled machining.  
Part 2: Introducing moulding and casting

<!--more-->


 
## 1. Computer-controlled machining


## Hardware and software

[Roland MX-50](https://www.rolanddga.com/products/3d/mdx-50-benchtop-cnc-mill) milling machine, 400x350x150mm (XYZ)

### CAM
* SRP player: creates tool paths from STL files
* [Fusion 360](https://www.autodesk.com/products/fusion-360/blog/getting-started-introduction-to-cam-and-toolpaths/)
* [fabmodules](http://fabmodules.org), and [here's the documentation](https://github.com/FabModules/fabmodules-html5)
* [fabmods](http://mods.cba.mit.edu/), and [here's the documentation](https://gitlab.cba.mit.edu/pub/mods)

:thought_balloon: Explore the machine

### Tooling

:thought_balloon: Look at some bits

- [milling bit types](http://mindworks.shoutwiki.com/wiki/Cutter_Types_(Mill)): ball-nose, flat-end mills
- [number of flutes](http://www.cs.cmu.edu/~rapidproto/students.03/zdb/project2/CNCflutes.htm)
- [coatings, centre-cutting and general cutter guide](https://www.cnccookbook.com/cnc-end-mill-guide/)
- [up/down cut](https://www.guhdo.com/blog/up-vs-down-shear-router-bits/)


## Workflow for CNC machining

* CAD: Design model, export as STL
* CAM: Generate toolpath + export G-code 
* Load into machine software 
* Set machine origin (XYZ0) values and verify bits
* Run job (cut fresh air)
* Run job (with stock)

### SRP Player Workflow

* Model size
    * Understanding margins - the job will be centered in the workpiece. So a 4x4cm job in a workpiece of 5x5cm will have an extra 0.5cm boder all round

* Setting model placement and cut type

* Creating tool paths
    * Roughing and finishing
    * Excluding margins

* Previewing
    * Check small features and corners
    * Check 

* Send to machine 
    * Set origins and check tools    


### Machine setup

See also <https://docs.google.com/document/d/14R-S-bQIisVIhJUZ70ZwEbi74LaQbHa-e2ixB39OMN8/edit#heading=h.9uukav7e0zv2>

* Fasten workpiece
* Set origins
* Check tools
* Check spindle speed

### Safety

* Sharp bits
* Protect the machine

## Terminology

### Milling

- [Speeds and feeds](https://en.wikipedia.org/wiki/Speeds_and_feeds)

    * Spindle speed (speed of rotation)
    * Feed rate (movement of bit acros the workpiece)

- Chip load: "the size or thickness of the chip that is removed with each flute per revolution"

    * Use a [chart](https://www.cutter-shop.com/information/chip-load-chart.html) to calculate feedrate and spindle speed 

### [Molding and casting](https://en.wikipedia.org/wiki/Casting_(metalworking)#Terminology)

* 'Pattern' or 'Model' or 'Mould Tool' https://en.wikipedia.org/wiki/Pattern_(casting)
* 'Mould' https://en.wikipedia.org/wiki/Molding_(process)
* 'Casting' from the mould https://en.wikipedia.org/wiki/Casting

## Design rules and considerations

### Cutting from above

* No [undercuts](http://www.acomold.com/image/molding-undercuts.jpg), you should be able to cut it all from above.
* Model placement and design

### Releasing the part

* Vertical walls should have [draft angles](https://www.dynacast.com/stuff/contentmgr/files/0/97f5240f1f1a61eac4d6f431cbd0b2d4/files/diecasting_design_tips_01.jpg)
* (Also helps with tool collisions)

### Bit must fit!

* Diameter, spindle length, shoulder
* Minimum feature size
* Interior corners vs exterior corners

### Material qualities

* Fast or slow spindle speed, feedrate 
* Adding fragile parts manually (e.g. using straws, [bolts](http://fab.academany.org/2018/labs/fablabbrighton/students/andrew-sleigh/assets/images/IMG_0597.jpg), sheets)

### Casting process

* Pour holes, vent holes
* 2-part molds 

### Mixing processes

* Time - quicker to make a box on the laser cutter, than to mill it from wax
* Adding fragile parts manually (e.g. using straws, bolts, sheets)

## Gotchas!

* Check tools in magazine 
* Set machine origin correctly
* Cut air first!!!






<hr />


## 2. Introducing moulding and tools

Positive solid tool > Negative flexible tool > Positive solid part:

![]({{ "/assets/positive-negative-positive-moulding.JPG" | relative_url }})


Negative solid tool > Positive flexible part:

![]({{ "/assets/pu-copper-ducks-out-mould.jpg" | relative_url }})

![]({{ "/assets/pu-copper-ducks-in-mould.jpg" | relative_url }})

<!-- 

- []({{ site.baseurl }}/assets/pu-copper-ducks-in-mould.jpg)
- [mould tools with registration](http://academy.cba.mit.edu/classes/molding_casting/tippy.png) -->
See also, [flexible parts](http://fab.cba.mit.edu/classes/863.13/people/crreed/weekly/week6.html)

### Mould tool considerations

- mixing: by weight or volume
- pouring: starting, filling, vent location
- bubbles: stirring, pouring, vibrating, painting, vacuum, pressure, time
- curing: polymerization, cross-linking, hydration, endothermic, exothermic
- demolding: draft angle, release agents (dilute dish soap, vaseline, talc, other), deformation

## Materials

### Making flexible moulds

Food safe silicon: [Polycraft Food Safe Addition Cure Silicone Moulding Making Rubber](https://www.mbfg.co.uk/food_safe_silicone.html)

* Safety (MSDS ([base](http://www.mbfgfiles.co.uk/datasheets/foodgrade_base_sds.pdf), [curing agent](http://www.mbfgfiles.co.uk/datasheets/foodgrade_curing_sds.pdf)))
    * Skin
    * Eyes
    * Respiratory
* Technical properties ([TDS](http://mbfgfiles.co.uk/datasheets/foodgrade_tech.pdf))
    * Pot time
    * Cure time
    * Endo- / exo-thermic (note: plaster of paris, resin)
* Protective gear
    * Personal: gloves, eye protection, lab coat
    * The space: trays, newspaper, bin bags
* Safe disposal
* Storage and shelf life

Take your time, focus, and prepare the space before you start.

### Casting solid objects

* 2-Part resin
* Plaster of Paris
* Cement
* Ice
* Chocolate


## Assignment

Create a 40 x 40 x 5 mini tile model in Fusion 360.
Mill it out of a block of wax.


### What do I need to do to pass?

Create the CAD model of your tile and mill it from wax. 

Demonstrate safe and tidy use of the CNC mill, and moulding and casting materials.

Document all your work on your student blog, with photos and videos to show what you did, what went wrong, and how you fixed it. Cite external sources where you have used someone else's work.


## Extra credit

Create a silicon mould and cast the finished part from chocolate or plaster of paris.

Try milling from another material, or experiment with adding parts to your mould tool manually. 

## Resources / find out more

* Fab Academy lecture notes (computer-controlled machining): <http://academy.cba.mit.edu/classes/computer_machining/index.html>  
* Fab Academy lecture notes (moulding&casting): <http://academy.cba.mit.edu/classes/molding_casting/index.html>  
* [Lecture from 2018 - computer-controlled machining](http://fab.academany.org/2018/lectures/fab-20180307.html)
* [Lecture from 2018 - moulding&casting](http://fab.academany.org/2018/lectures/fab-20180321.html)

* [guide to CNC machining a mould tool using the 1610 mini CNC machine](https://fablabbrighton.github.io/digital-fabrication-module/guides/guide-milling-mould-tool.html)
* [CNC design guide](https://www.3dhubs.com/knowledge-base/how-design-parts-cnc-machining) 
* [Make: Design for CNC book](https://www.amazon.co.uk/Make-Practical-Techniques-CNC-routed-Furniture/dp/1457187426) 