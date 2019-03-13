---
layout: page
title:  "Week 8: computer-controlled machining + moulding and casting"
date:   2018-3-5
author: Derek Covill
---

Part 1: Introducing computer-controlled machining
Part 2: Introducing moulding and casting

<!--more-->


## Prep for this week's class

Watch the corresponding Fab Academy lectures. We'll be covering part of this content. 

* Fab Academy lecture notes (computer-controlled machining): <http://academy.cba.mit.edu/classes/computer_machining/index.html>  
* Fab Academy lecture notes (moulding&casting): <http://academy.cba.mit.edu/classes/molding_casting/index.html>  
* [Lecture from 2018 - computer-controlled machining](http://fab.academany.org/2018/lectures/fab-20180307.html)
* [Lecture from 2018 - moulding&casting](http://fab.academany.org/2018/lectures/fab-20180321.html)

## Baseline 

Who has:

* done any workshop machining or CNC machining?
* made a mould?
* done any casting?

## Resources (computer-controlled machining)
- [CNC design guide](https://www.3dhubs.com/knowledge-base/how-design-parts-cnc-machining) 
- [Make: Design for CNC book](https://www.amazon.co.uk/Make-Practical-Techniques-CNC-routed-Furniture/dp/1457187426)

## Computer-controlled machining
[**computer-controlled machining**](http://academy.cba.mit.edu/classes/computer_machining/index.html "computer controlled machining")

*   our machines
    *   office (Des): [1610 3-axis router](https://www.ebay.co.uk/itm/CNC-Wood-Router-1610-Mini-Milling-Carving-Engraving-Machine-GRBL-Control-3-Axis/162556175066?epid=10003409492&hash=item25d91a62da:g:TDwAAOSwHUhZ~~zy), 160x100x45mm (XYZ)
    *   E28 (Gary/Jon): [Imes-Icore M40 3-axis](https://www.imes-icore.de/eng/flatcom-cnc-milling-machine-series.html) router, 1000x900x250mm (XYZ)
    *   EM13 (Des): [Roland MX-50](https://www.rolanddga.com/products/3d/mdx-50-benchtop-cnc-mill) milling machine, 400x350x150mm (XYZ)
    *   E19 (Adam Cable): [Herco VM10UI 5-axis](http://www.hurco.com/en-gb/machine-tools/machining-centres/5-axis-vertical/pages/trunnion-table.aspx) milling machine, 400x400x400mm (XYZ)
*   software
    *   [Solidworks CAM](https://www.youtube.com/watch?v=pPxH-JGTCK4)
    *   [SolidCAM](https://www.solidcam.com/professor/solidcam-modules-overview/) , [demo](https://youtu.be/di-VxpxAUGQ) , [tutorials](https://www.solidcam.com/professor/solidcam-jumpstart/),  [machine building](https://youtu.be/R3pW8RenKZk) (see simulation below)
    *   [Fusion 360](https://www.autodesk.com/products/fusion-360/blog/getting-started-introduction-to-cam-and-toolpaths/)
*   SRP player (Roland MX-50)
*   [fabmodules](http://fabmodules.org)
*   [fabmods](http://mods.cba.mit.edu/)

### software to run CNC machines
- [GRBL (standard)](https://github.com/gnea/grbl)
- [GRBLcontrol - PC/linux only (runs the small 1610 machine in fablab)](https://github.com/trasz/grblControl)
- ??? (Imes-Icore M40 in E28)
- [swift cut (plasma cutter)](https://swift-cut.com/)
- [VPanel (Roland MX-50 in fablab)](http://support.rolanddga.com/Docs/Documents/departments/Technical%20Services/Downloads/MDX-50_INS_EN_R2.pdf)
- [Winmax (Herco VM10UI in Adam's workshop)](http://www.hurco.com/en-us/cnc-machine-tools/our-control/pages/winmax.aspx)
- [VCarvePro (AXYZ at Grand Parade)](https://www.vectric.com/products/vcarve-pro)
- [Marlin](http://marlinfw.org/)
- [Mach3](https://www.machsupport.com/software/mach3/)

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

### process
- CAD > CAM: generate toolpath + export G-code > load into machine software > run machine

## rules for making simple mould tools
1. Vertical walls should have [draft angles](https://www.dynacast.com/stuff/contentmgr/files/0/97f5240f1f1a61eac4d6f431cbd0b2d4/files/diecasting_design_tips_01.jpg)
2. There should be no [undercuts](http://www.acomold.com/image/molding-undercuts.jpg)

## Assignment
- create a 30x30x5 mini tile part in Fusion 360 and generate the toolpath to cut it out of a solid block 50x50x10mm using a 3mm flat or ball-nose end mill (ideally include 3deg of draft angle on all vertical surfaces). It's best to be oriented with the front view being the top of your part. All stepdowns should be 1mm and stepovers should be 1.5mm. Document all this on your blog. Set up your stock as indicated below.
![stock-dimensions]({{ site.baseurl }}/assets/30x30x5-Part-from50x50x10-stock.jpg)

## Extra credit
- cut the tile from the solid block of 50x50x10mm foam or wax using a CNC milling machine
- cast an elastic material (e.g. silicone or jelly) into the cavity and wait for this to set
- remove the new elastic mould tool
- cast a molten liquid (e.g. resin or chocolate) into your mould tool to create a solid part

### What do I need to do to pass?
- create the cad model of your tile and generate the toolpath and document this on your blog.

