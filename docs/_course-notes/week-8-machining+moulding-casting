---
layout: page
title:  "Week 8: computer-controlled machining + moulding and casting"
date:   2018-3-5
author: Derek Covill
---

Introducing computer-controlled machining + moulding and casting.

<!--more-->


## Prep for this week's class

Watch the corresponding Fab Academy lecture. We'll be covering part of this content. 

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
    *   GRBL
    *   [arduino](https://www.arduino.cc/)
*   hardware
    *   [pololu](https://www.pololu.com/)
    *   [arduino](https://www.arduino.cc/)
*   [milling bit types](http://mindworks.shoutwiki.com/wiki/Cutter_Types_(Mill)): ball-nose, flat-end mills
*   good cutters:
    *   [0.4mm single flute](https://www.damencnc.com/en/mini-end-mills-one-flute-0-40mm-818/a1132?c=203) (DamenCNC)
    *   [0.4mm single flute](https://www.sorotec.de/shop/End-Mill-Single-Flute--0-4mm.html "Sorotec single flute 0.4mm") (Sorotec)

*   [speeds n feeds](https://en.wikipedia.org/wiki/Speeds_and_feeds)
*   [cnc training guides](https://www.cnccookbook.com/online-cnc-training-courses-guides-help/?utm_source=ActiveCampaign&utm_medium=email&utm_content=Jump+start+your+CNC+New+Year&utm_campaign=10FreeCNCCourses)
*   process: CAD > CAM: generate toolpath + export G-code > load into machine software > run machine
*   [documentation](https://docs.google.com/document/d/1R7PvT-j3l-Mz94qoynsk3z2aP2Ewtweq85q_kYWCGpI/edit?usp=sharing)
*   assignment
    *   individual: create simulation toolpath using SolidCAM, SolidworksCAM, Fusion 360, or other software using either a 3mm ball-nose or flat-end milling bit. Later we will arrange to mill these. 
    *   group: make the [documentation](https://docs.google.com/document/d/1R7PvT-j3l-Mz94qoynsk3z2aP2Ewtweq85q_kYWCGpI/edit?usp=sharing) awesome






### Our machines REDONE
- office (Des): 1610 3-axis router, 160x100x45mm (XYZ)
- E28 (Gary/Jon): Imes-Icore M40 3-axis router, 1000x900x250mm (XYZ)
- EM13 (Des): Roland MX-50 milling machine, 400x350x150mm (XYZ)
- E19 (Adam Cable): Herco VM10UI 5-axis milling machine, 400x400x400mm (XYZ)
- plasma 


### CAM software
- Solidworks CAM
- SolidCAM , demo , tutorials,  machine building (see simulation below)
- Fusion 360
- SRP player (Roland MX-50)
- fabmodules.org
- fabmods (http://mods.cba.mit.edu/)

### software to run CNC
- GRBL control (1610)
- ??? (Imes-Icore M40)
- swift cut (plasma)
- VPanel (Roland MX-50)
- Winmax (Herco VM10UI)

- VCarvePro (AXYZ)
- Marlin 
- Mach3

### hardware to run CNC
- pololu
- arduino

### tooling
- drill bits vs router bits vs end mills
- flutes
- coatings
- center-cutting
- up/down cut
- flat/ball end
   
- milling bit types: ball-nose, flat-end mills

### speeds n feeds
- chip load: ~ 0.001-0.010"
- feed rate (inches per minute) / (RPM x number of flutes) 
- cut depth: ~ tool diameter
- step-over: ~ tool diameter/2

### process
- CAD > CAM: generate toolpath + export G-code > load into machine software > run machine

## CNC rules
1. Vertical walls should have [draft angles](https://www.dynacast.com/stuff/contentmgr/files/0/97f5240f1f1a61eac4d6f431cbd0b2d4/files/diecasting_design_tips_01.jpg)
2. There should be no [undercuts](http://www.acomold.com/image/molding-undercuts.jpg)

## Resources (moulding&casting)

## Assignment
- create a 30x30x5 mini tile part in Fusion 360 and generate the toolpath to cut it out of a solid block 50x50x10mm using a 3mm flat end mill (ensure > 3deg of draft angle on all vertical surfaces)

## Extra credit
- cut the tile from the solid block of 50x50x10mm foam or wax using a CNC milling machine
- cast an elastic material (e.g. silicone or jelly) into the cavity and wait for this to set
- remove the new elastic mould tool
- cast a molten liquid (e.g. resin or chocolate) into your mould tool to create a solid part

### What do I need to do to pass?
- create the cad model of your tile and generate the toolpath.
???- vacuum form over a small part to create a mould, and cast something into the mould

