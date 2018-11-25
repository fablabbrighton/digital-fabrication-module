---
layout: page
title:  "Week 3: Laser cutter: computer-controlled cutting (CNC)"
date:   2018-11-23
---

Introducing the laser cutter and 2D-3D assembly.

<!--more-->


## Sources
* Course content derived from Fab Academy: <http://academy.cba.mit.edu/classes/computer_cutting/index.html>  
* Neil’s lecture from 2018 (Fab-20180207D_Lesson03): [Fab Academy 20180207 Recordings](http://fab.academany.org/2018/lectures/fab-20180207.html)

## Assignment

### Group assignment

Characterise your lasercutter, making test part(s) that vary cutting settings and dimensions
Make test cuts, vary power, speed and frequency for different materials. Document settings for different materials and thicknesses
Make kerf tests to find good settings for different materials. Use these results for your own (parametric) design 

<!-- Do we need a group assignment? Is it feasible to do? -->

### Individual assignment


Design, lasercut, and document a parametric  [press-fit construction kit](http://fab.cba.mit.edu/classes/863.12/people/salzberg/week2.html), accounting for the lasercutter kerf, which can be assembled in multiple ways

----

## An overview of CNC cutting tools

In this module, we’re going to focus on the laser cutter (optionally also the vinyl cutter)

### Knife

Vinyl cutters - under-utilised tools in Fablabs. e.g.
* [Roland](https://www.rolanddga.com/products/vinyl-cutters)
* [Zund](https://www.zund.com/)
* [Othercutter](https://www.youtube.com/watch?v=PG9lJOnNTzQ)
* [ultrasonic](https://www.honda-el.co.jp/en/industry)

### Laser
Most used machine in the lab  
Huge spectrum of capability:  
* [PHAROS](http://www.lightcon.com/Product/PHAROS.html)  - “disassembles material on an atomic scale, lets you do laser cutting down to microns”  / $100k  
* [Epilog](http://www.epiloglaser.com/product_line.htm)    - we have a Helix  / £10k  
* [Full Spectrum](http://fslaser.com/)  Hobbyist lasers / $1k


### Plasma

* [Forest Scientific](http://forestscientific.com/cnc-plasma-cutters)
* [Torchmate](https://torchmate.com/) 

### Waterjet

* [OMAX](https://www.omax.com/)
* [Flow](https://www.flowwaterjet.com/) – Can cut anything / $100k / Uses consumables - you must add new garnet, and remove garnet sludge
* [WAZER](https://www.wazer.com/)   - a kickstarter project, becoming more accessible

### Hot wire

Killer app: architectural decoration and special effects in foam.

* [FROGWire](http://www.3dcutting.com/solutions/frogwire.html)
* [Hotwire](http://www.hotwiresystems.com/hot-wire-cnc-foam-cutters)   
* [MTM](http://ng.cba.mit.edu/show/video/14.08.modular.mp4) Good candidate for a DIY project: just need two positional ends and a resistive wire
 

## Computer Aided Design (CAD) software

### We use

Mostly **Fusion360, Rhino, Solidworks** for 3D; **Illustrator or Inkscape** for 2D

### Others

* [Inkscape](http://www.inkscape.org/) [video](http://academy.cba.mit.edu/classes/computer_design/inkscape.mp4) 
* [Rhino](http://www.rhino3d.com/)
* [Grasshopper](http://www.grasshopper3d.com/) [video](https://www.youtube.com/watch?v=mZ_1jC2FrnY&t=2s) 
* [Blender](https://www.blender.org/)
* [Sverchok](http://nikitron.cc.ua/sverch/html/main.html) 
* [FreeCAD](https://www.freecadweb.org/)
* [Sketcher](https://www.freecadweb.org/wiki/Sketcher_Workbench) [video](http://academy.cba.mit.edu/classes/computer_design/freecadsketch.mp4) 
* [Fusion 360](http://www.autodesk.com/products/fusion-360/overview)
* [Slicer](https://apps.autodesk.com/FUSION/en/Detail/Index?id=8699194120463301363&os=Win64&appLang=en) 
* [SolidWorks](http://www.solidworks.com/)
* [xDesign](https://xdesign.solidworks.com/) 
* [Onshape](https://www.onshape.com/)
* [Kiri:Moto](https://appstore.onshape.com/apps/CAM/EAAEWYIOMQKBENEMYW2N7MF253CT4WYL6SUJGEY=/description) 
* [Antimony](https://github.com/mkeeter/antimony)  [video](http://academy.cba.mit.edu/classes/computer_design/antimony.mp4) 
* [Pepakura](http://www.tamasoft.co.jp/pepakura-en/)
* [VisiCut](http://hci.rwth-aachen.de/visicut)
* [flatfab](http://flatfab.com/)
* [ExactFlat](https://www.exactflat.com/) 
* [mods](http://mods.cba.mit.edu/?program=programs/frep/gears) 



### Parametric design

* Cardboard comes in different thicknesses
* Lasers cut with different kerfs
* Human bodies come in different shapes and sizes

Inkscape is not parametric, Rhino and Fusion 360 are.


## Computer Aided Manufacturing ([CAM](https://en.wikipedia.org/wiki/Computer-aided_manufacturing))

CAD is design, CAM translates a design file into a format the machine understands and communicates with the machine.

Typically through printer driver (accessible in Print dialog on your 2D CAD software)  
But we can also talk to the mchine at a lower level using [Fab Modules](http://fabmodules.org) or Mods


## The Laser cutter

### Applications

* Cutting or marking/engraving by varying power  
* Raster or [vector](http://academy.cba.mit.edu/classes/computer_cutting/gray.jpg) mode
* Screen printing, by making a [halftone](http://academy.cba.mit.edu/classes/computer_cutting/halftone.jpg) (See [holes](http://academy.cba.mit.edu/classes/computer_cutting/holes.jpg), [path](http://academy.cba.mit.edu/classes/computer_cutting/halftone.png)) 
* Press-fit construction (example: [GIK](http://academy.cba.mit.edu/classes/computer_cutting/gik.jpg), [gik.cad](http://academy.cba.mit.edu/classes/computer_cutting/gik.cad), [gik.png](http://academy.cba.mit.edu/classes/computer_cutting/gik.png))

### Joints

[Examples](http://academy.cba.mit.edu/classes/computer_cutting/joints.jpg)

Easy to design \<--> Strongest properties

* Slot - simplest, hard to align
* Chamfer - rounded corners help align parts, and can compress materials into slots (eg corrugated cardboard). But still relies on sliding friction
* Bistable (bump and slot), behaves very differetly for different materials
* Flexure - design a bendable part with controllable flex
* Pinned - secure joint with an orthogonal constraint (see also [wedged mortise and tenon](https://www.canadianwoodworking.com/tipstechniques/wedged-mortise-tenon))

### Tolerances 

* Slop vs security (range is about 0.1mm)
* Brittle material vs compressible material
* Parametric design is your friend

### 3D shapes

* Kerfing (incomplete cut)
* [Flexures, living hinges](http://academy.cba.mit.edu/classes/computer_cutting/flexures.png) (enables twists and bends). See also [Inkscape living hinge extension](https://inkscape.org/~drphonon/★living-hinge-creator)
* Extreme example, a [moving platform](http://academy.cba.mit.edu/classes/computer_cutting/56836505.pdf) without moving parts (gears, bearings)


### Lasers (_Light Amplification by Stimulated Emission of Radiation_)

See Neil's lecture (@ 45 mins) for technical details  
CO<sub>2</sub> laser: good for wood, card, acrylic, etc. Need a fiber laser to cut metal.

### Cutting mechanisms
* burning
* melting
* evaporation
* ablation

The material has to go somewhere, ...

### Airflow

* Exhaust - draws combustible material out. (Machine: Extractor)
* Assist - injects air at the cutting point. (Machine: Compressor)

If it's not strong enough, that material stays around - Bad news  
You shouldn't see smoke hanging around in laser cutting chamber  
Exhaust fumes are very bad news.  
Plastic will outgas for a minute after cutting. Leave the lid closed for a minute


### Kerf

Some material is removed with the cut.  
Some drivers (e.g. mods) allow for this, with offsetting.  
Otherwise, you should allow for this in your design (parametrically!)

### Safety
[All laser cutters want to catch on fire](http://academy.cba.mit.edu/classes/computer_cutting/fire.jpg)   
Card, MDF, plywood and acrylic are all really close to combusting when cutting.  
Don't step away from the machine. Always supervise.  
Initial combustion: open the lid. Otherwise, smother or use the fire extinguisher.
**check**


### Materials

* Cardboard - the good stuff bows, not kinks. Use old boxes. Very forgiving for joints
* [Plywood](https://www.towerhobbies.com/cgi-bin/wti0091p?&P=ML&C=RCC&V=RMX&D=Revell-Wood---Plywood) - Real thickness != real thickness - use the callipers.
* [PMMA/acrylic/plexiglass/perspex/lucite](https://www.mcmaster.com/#acrylic/=1bgkrkx)   [glue](https://www.mcmaster.com/#standard-acrylic-glue/=1bgkitd)   [bend](https://makezine.com/2013/02/06/workshop-wednesday-heat-bending-acrylic-enclosures)   
* [POM/delrin/acetal](http://www.mcmaster.com/#acetal-homopolymer-sheets) - more elastic than acrylic

### No-gos
* No PVC - releases chlorine
* Never put a material into the cutter unless you know where it came from - no random plastic.
* Never put anything shiny into a CO<sub>2</sub> laser (e.g. metal)

Laser optics need to be kept clean (by who?)

### Settings

(See laser printer driver dialog.)
![laser-printer-driver-dialog.jpg]({{ "/assets/laser-printer-driver-dialog.jpg" | relative_url }})

* Power - too much melts, too little doesn't cut. Use multiple passes. 
* Speed - too slow can cause combustion, too slow doesn't cut
* Pulse rate/Frequency - too close can melt, too far apart can leave gaps
* Coordinate system, origin is top left
* Vector mode for cutting, raster mode for engraving (but interesting grey areas for experimentation)

