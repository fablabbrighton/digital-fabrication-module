---
layout: page
title:  "3D Fabrication: Milling Machine"
date:   2020-01-02
author: Andrew Sleigh
---

Part 1: Introducing computer-controlled machining.  
Part 2: Introducing moulding and casting

<!--more-->

## Resources (computer-controlled machining)

* Fab Academy lecture notes (computer-controlled machining): <http://academy.cba.mit.edu/classes/computer_machining/index.html>  
* Fab Academy lecture notes (moulding&casting): <http://academy.cba.mit.edu/classes/molding_casting/index.html>  
* [Lecture from 2018 - computer-controlled machining](http://fab.academany.org/2018/lectures/fab-20180307.html)
* [Lecture from 2018 - moulding&casting](http://fab.academany.org/2018/lectures/fab-20180321.html)

* [guide to CNC machining a mould tool using the 1610 mini CNC machine](https://fablabbrighton.github.io/digital-fabrication-module/guides/guide-milling-mould-tool.html)
* [CNC design guide](https://www.3dhubs.com/knowledge-base/how-design-parts-cnc-machining) 
* [Make: Design for CNC book](https://www.amazon.co.uk/Make-Practical-Techniques-CNC-routed-Furniture/dp/1457187426)

## Computer-controlled machining
[**computer-controlled machining**](http://academy.cba.mit.edu/classes/computer_machining/index.html "computer controlled machining")

## Hardware


[Roland MX-50](https://www.rolanddga.com/products/3d/mdx-50-benchtop-cnc-mill) milling machine, 400x350x150mm (XYZ)


### tooling

- [milling bit types](http://mindworks.shoutwiki.com/wiki/Cutter_Types_(Mill)): ball-nose, flat-end mills
- [number of flutes](http://www.cs.cmu.edu/~rapidproto/students.03/zdb/project2/CNCflutes.htm)
- [coatings, centre-cutting and general cutter guide](https://www.cnccookbook.com/cnc-end-mill-guide/)
- [up/down cut](https://www.guhdo.com/blog/up-vs-down-shear-router-bits/)

### speeds n feeds

- [speeds n feeds](https://en.wikipedia.org/wiki/Speeds_and_feeds)
- [chip load: ~ 0.001-0.010"](https://www.cutter-shop.com/information/chip-load-chart.html)
- feed rate (inches per minute) / (RPM x number of flutes) 
- cut depth: ~ tool diameter
- step-over: ~ tool diameter/2


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
- [GRBLcontrol - PC/linux only (runs the small 1610 machine in fablab)](https://github.com/trasz/grblControl)
- ??? (Imes-Icore M40 in E28)
- [swift cut (plasma cutter)](https://swift-cut.com/)
- [VPanel (Roland MX-50 in fablab)](http://support.rolanddga.com/Docs/Documents/departments/Technical%20Services/Downloads/MDX-50_INS_EN_R2.pdf)
- [Winmax (Herco VM10UI in Adam's workshop)](http://www.hurco.com/en-us/cnc-machine-tools/our-control/pages/winmax.aspx)
- [VCarvePro (AXYZ at Grand Parade)](https://www.vectric.com/products/vcarve-pro)
- [Marlin](http://marlinfw.org/)
- [Mach3](https://www.machsupport.com/software/mach3/)


## Workflow for CNC machining
- CAD > CAM: generate toolpath + export G-code > load into machine software > set XYZ0 values > run machine (cut fresh air) > run machine (with stock)

## Design rules and considerations

Axes
Bit size and shape
Material qualities



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

## rules for making simple mould tools
1. Vertical walls should have [draft angles](https://www.dynacast.com/stuff/contentmgr/files/0/97f5240f1f1a61eac4d6f431cbd0b2d4/files/diecasting_design_tips_01.jpg)
2. There should be no [undercuts](http://www.acomold.com/image/molding-undercuts.jpg), you should be able to cut it all from above.

## Assignment
- create a 30x30x5 mini tile part in Fusion 360 and generate the toolpath to cut it out of a solid block (50x50x10mm) using a 3mm flat or ball-nose end mill (ideally include 3deg of draft angle on all vertical surfaces). It's best to be oriented with the front view being the top of your part. All stepdowns should be 1mm and stepovers should be 1.5mm. Document all this on your blog. Set up your stock as indicated below.
![stock-dimensions]({{ site.baseurl }}/assets/30x30x5-Part-from50x50x10-stock.jpg)
- [here's a full guide](https://fablabbrighton.github.io/digital-fabrication-module/guides/guide-milling-mould-tool.html) showing how to setup the CAM for this. The guide also shows how to setup the machine, cut out the stock material and then to cast silicone into it also, although these steps are not required for this assignment - they're optional - see below). 

## Extra credit
- cut the tile from the solid block of 50x50x10mm foam or wax using a CNC milling machine
- cast an elastic material (e.g. silicone or jelly) into the cavity and wait for this to set
- remove the new elastic mould tool
- cast a molten liquid (e.g. resin or chocolate) into your mould tool to create a solid part

### What do I need to do to pass?
- create the cad model of your tile and generate the toolpath and document this on your blog, ideally including an animation of the toolpath (like the one provided on the guide). 

