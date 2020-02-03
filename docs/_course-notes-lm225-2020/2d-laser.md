---
layout: page
title:  "2D Fabrication: Laser cutter"
date:   2020-01-02
author: Andrew Sleigh
---

Precise cutting of thin sheet materials

<!--more-->

## Prep for this week's class

## Baseline 

No knowledge of laser cutters or software assumed. However, you will find this session much easier if you have spent some time playing with vector graphics software:

* Install and try out some 2D vector software ([handbook](https://fablabbrighton.github.io/digital-fabrication-module/course-notes-lm225-2020/handbook#things-you-will-need))

Main software we will be using:

* Illustrator: Commerical, industry-standard in creative professions, nice to use, but not optimised for laser. Installed in labs and [available with discount, £16-20/month](https://www.adobe.com/uk/creativecloud/buy/students.html)

* Inkscape: free and open source. A bit fiddly, but many useful extensions for machine control.

* Fusion 360: Really 3D design softwae, but does have 2D sketching tools, and can export 2D artwork as DXF. Also has very useful parametric design tools (great for fine tuning artwork for the laser cutter). Free for [students](https://www.autodesk.co.uk/products/fusion-360/students-teachers-educators) and [hobbyists](https://www.autodesk.com/campaigns/fusion-360-for-hobbyists).


Other options:

* [Affinity Designer](https://affinity.serif.com/en-gb/designer/) (Commercial, £20-50, Windows, Mac and iPad)
* [Bez for iPad](https://www.juicybitssoftware.com/bez/) (has a free version)



<!-- NOTE TO SELF: FOCUS ON GETTING STARTED WITH MACHINE, COVER DETAIL NEXT WEEK -->

<!-- fa notes -->


### Parametric design

* Cardboard comes in different thicknesses
* Lasers cut with different kerfs
* Human bodies come in different shapes and sizes

Inkscape is not parametric, Rhino and Fusion 360 are.

Example in Fusion 360: [minimal-parametric-laser-cutter-demo](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/3d-models/minimal-parametric-laser-cutter-demo)

![minimal-parametric-laser-cutter-demo-screenshot.png]({{ "/assets/minimal-parametric-laser-cutter-demo-screenshot.png" | relative_url }})




## Computer Aided Manufacturing ([CAM](https://en.wikipedia.org/wiki/Computer-aided_manufacturing))

CAD is design, CAM translates a design file into a format the machine understands and communicates with the machine.

Typically through printer driver (accessible in Print dialog on your 2D CAD software)  
But we can also talk to the machine at a lower level using [Fab Modules](http://fabmodules.org) or [Mods](http://mods.cba.mit.edu)


## The laser cutter

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
Exhaust fumes are very bad news  
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
Laser optics need to be kept clean, otherwise, heat can build up (so avoid smoke)

<span class="wip">WIP</span>: Check safety procedures


### Materials

* Cardboard - the good stuff bows, not kinks. Use old boxes. Very forgiving for joints
* [Plywood](https://www.towerhobbies.com/cgi-bin/wti0091p?&P=ML&C=RCC&V=RMX&D=Revell-Wood---Plywood) - Real thickness != real thickness - use the callipers.
* [PMMA/acrylic/plexiglass/perspex/lucite](https://www.mcmaster.com/#acrylic/=1bgkrkx)   [glue](https://www.mcmaster.com/#standard-acrylic-glue/=1bgkitd)   [bend](https://makezine.com/2013/02/06/workshop-wednesday-heat-bending-acrylic-enclosures)   
* [POM/delrin/acetal](http://www.mcmaster.com/#acetal-homopolymer-sheets) - more elastic than acrylic

### No-gos
* No PVC - releases chlorine
* Never put a material into the cutter unless you know where it came from - no random plastic.
* Never put anything shiny (e.g. metal) into a CO<sub>2</sub> laser 


## Preparing artwork (for vector cutting)

* 2D vector file (EPS or DXF)
* Make the format as simple as possible
* All shapes no fill, nd 0.001mm stroke
* Laser origin is top left



## How to use the laser cutter

See Fab Academy docs here: <https://docs.google.com/document/d/1kDd0A60eJdmJgIRt-zmAJwxszw0Gd61VXqHKnizv6hg/edit>

### Place material
* Consider airflow
* Alignment against the rulers
* Support to distance the material from the bed
* Flat surface - consistent z-height



### Set origins and focus

* Use laser pointer
* Set x and y origins
* Use focus tool to set z-origin


### Settings


![laser-printer-driver-dialog.jpg]({{ "/assets/laser-printer-driver-dialog.jpg" | relative_url }})

* Power - too much melts, too little doesn't cut. Use multiple passes. 
* Speed - too slow can cause combustion, too slow doesn't cut
* Pulse rate/Frequency - too close can melt, too far apart can leave gaps
* Coordinate system, origin is top left
* Vector mode for cutting, raster mode for engraving (but interesting grey areas for experimentation)

### Extraction

* Turn on the BOFA extractor (speed approx 330m3h)
* Turn on the air compressor

### Whilst it's cutting
* Always observe the cutting closely

### After the cut
* Leave the lid closed with the extractor on for 30 seconds
* If you mess up the bed, clean it up - take it to the sink and carefully clean it without bending the sheet







<!-- end of FA notes -->

## 3D assembly and forming shapes

Maybe go into this in more detail next week?

## Calibration pieces

Purpose
Types
See FA docs?

## Assignment

Cut a series of test pieces to measure kerf and effect of different settings:
* Kerf
* Engraving effects
* Fit of assembled parts
* Scoring, folding
* Damage, edge qualities

Make (start) a reference doc of different settings 


Document all your work on your student blog, with photos and videos to show what you did, what went wrong, and how you fixed it. Cite external sources where you have used someone else's work.



### What do I need to do to pass? (40%)


### Extra credit (50-100%)




## For next week

---

## Materials we need this week

* Card
* MDF
* Acrylic


