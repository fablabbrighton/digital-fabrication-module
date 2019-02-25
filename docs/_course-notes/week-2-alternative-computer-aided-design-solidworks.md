---
layout: page
title:  "Week 2: Computer-Aided Design (Solidworks)"
date:   2018-2-5
author: Derek Covill
---

Introducing parametric modelling.

<!--more-->

## Prep for this week's class

Watch the corresponding Fab Academy lecture. We'll be covering part of this content. 

* Fab Academy lecture notes: <http://academy.cba.mit.edu/classes/computer_design/index.html>  
* [Lecture from 2019](https://vimeo.com/314594035)

## Baseline 

Who has:

* Used CAD software
* Used parametric software
* Produced 2D drawings

# Solidworks (PC only)

is...
1. Parametric: everything is driven/adjusted by numbers (length, diameter, thickness, colour, etc). 
2. Feature-based: geometry is created with features
3. Associative: parts, assembles, drawings are linked - a change in one will filter to all

SW can do: FEA, CFD, motion analysis, electronic wiring, lots more!

Student licences- £6 for a USB from computer store, 1st Floor Watts Building. Renew at the start of each academic year. 

[Certification exams:](https://www.solidworks.com/sw/support/mcad-certification-programs.htm) we will provide these: TBA

## Resources:
- Start with these.....Help menu > tutorials (Lesson1: parts, Lesson2: Assembles, Lesson3: drawings) - these are excellent, make notes, observe everything and master them. 
- [lesson 1: parts video](https://www.youtube.com/watch?v=HKSo99hGDd4), and [here is the part to download](https://drive.google.com/file/d/12AT58ieVu98Ri9V_XwIrEPaPela-h4lc/view?usp=sharing)
- [lesson 2: assemblies video](https://www.youtube.com/watch?v=yGvZ3Jly1mI), and [here is a .zip file with the assembly to download](https://drive.google.com/file/d/1oaL8U4Sb--CpLDMmL2JXY45wOh4JSLY8/view?usp=sharing)
- [lesson 3: drawings video](https://www.youtube.com/watch?v=lX85kgun8sE)
- use the help (online also)
- Grabcad/Thingyverse/etc (filter for Solidworks models). 
- any existing models to reverse engineer
- Lynda.com (for UoB: www.brighton.ac.uk/lynda) - Solidworks 20XX essentials. 
- [sketching exercises](https://drive.google.com/open?id=1kcsn3ghW-dgm7xf_htp9wL9p7MROS2PX)
- [part modelling exercises](https://drive.google.com/open?id=1fmFIsjV-P9DPdEKxaB_PEqnUaqnMnYti)

## Layout:
- [user interface](http://help.solidworks.com/2018/english/SolidWorks/sldworks/c_user_interface_overview.htm?id=3142cd59ed8f4abd874df330c405866b#Pg0)

Units: see bottom right hand corner (use millimeters!)

## Navigation:
MIDDLE DOES EVERYTHING! 
- zoom: scroll middle 
- rotate: hold middle 
- pan: hold middle + CTRL

## File types:
1. [Parts: as it would be manufactured](https://i.ytimg.com/vi/zNDwvsU5Dko/maxresdefault.jpg), and [here is an example part to download](https://drive.google.com/open?id=1cqLD5eFEoibOEE9s5JtzpHosdMc1vfPv)
2. [Assemblies: a collection of parts (and/or of other sub-assemblies)](https://www.javelin-tech.com/blog/wp-content/uploads/2017/07/solidworks-rigid-subassembly-780x417.jpg), and [here is a .zip file with parts and an assembly file](https://drive.google.com/open?id=149qhKK8XwrYCRW4EAZ82ja-q1--MNDmP)
3. Drawings: orthographic of [parts (with dimensions)](https://drive.google.com/file/d/1_gLnEhN6V9yIvXOtrcoiv1nagzX694tu/view?usp=sharing) and [assemblies (with NO dimensions, with balloons + bill of materials (BOM))](https://drive.google.com/file/d/1x1ZnpyDDDSDOvsiO_MYekYaAqF7jx3gg/view?usp=sharing)....or [both](https://ayoqq.org/images/solidworks-drawing-solidworks-assembly-13.jpg). 

[difference between Fusion 360 and Solidworks](https://all3dp.com/2/fusion-360-vs-solidworks-cad-software-compared-side-by-side/)

## Basic part modelling process:
1. Create new sketch
2. Select plane or flat surface to sketch on
3. Draw 2D sketch (open or closed)
4. Exit sketch
5. Use sketch to create feature

Follow these steps, be methodical

### Sketch entities: (note different options for each)
- line
- arc
- rectangle
- circle
- spline (avoid where possible)
- use smart dimensions ALWAYS
- toggle construction lines on/off

### Sketch tools:
- convert entities
- offset entities
- trim (oh power trim!!)
- mirror/pattern

### Sketch relations:
- coincident
- concentric
- equal
- parallel
- perpendicular
- colinear
- coradial

### Basic features: 
- extrude/cut
- revolve/cut
- hole wizard
Intermediate features:
- sweep/cut
- loft/cut
- pattern
- mirror

## Early challenge:
- create a 6-sided die (10x10x10mm, R1mm fillets on all faces, D2mm holes 0.5mm deep (opposing sides add up to 7)
- all details must be dimensioned fully
- approach this in different ways, aim to do it as fast as you can
- record < 1min, excellent < 5min, ok < 15min
- [2019 leaderboard](https://docs.google.com/document/d/1r5j0Bj-RQjewX0iajl6O0TMxy5sYbaCDed5bEuyTX-0/edit?usp=sharing)
- [example die part file to download](https://drive.google.com/open?id=1zCTDj-7bnFJ6TkA2ZZHRS2rKuS0ElQmB)

## Second challenge:
- create a bicycle stem using extrude/cut, fillets. You don't need to create extra planes, but you can if you wish.
- this is an exercise in understanding how to use your reference geometry (planes) well - it is quite a spacial awareness challenge!
- [here is a completed version with all the trimmings](https://drive.google.com/open?id=1bkDZ35xufDL4OiQX7E2IOrJp5gVmQZP0)
- start with the three basic cylinders, then add details after.
![here are the dimensions of the stem]({{ site.baseurl }}/assets/stem-dimensions.jpg)
- for an extra challenge, angle the head tube (vertical tube) by 7 degrees to the horizontal

## Useful tools:
- [toolbox (nuts, bolts, gears etc)](http://help.solidworks.com/2018/english/solidworks/toolbox/t_toolbox_activating_add_ins.htm)
- [Traceparts CAD models](https://www.traceparts.com/en)
- also Grabcad/Thingyverse/etc

## Assemblies
- can mate: vertices, lines/centrelines, faces, planes
- coincident, offset, parallel, concentric etc
- [standard mates](https://drive.google.com/file/d/1oaL8U4Sb--CpLDMmL2JXY45wOh4JSLY8/view?usp=sharing)
- [advanced mates: limits](https://drive.google.com/file/d/1tWA9bw8Dneyldqj9AoR2EX2uB0QHzJVJ/view?usp=sharing)
- [mechanical mate: gears](https://drive.google.com/file/d/1c7oQpajB9dheMjG9hkhUYjp4p7x_FOl0/view?usp=sharing)
- [mechanical mate: cams](https://drive.google.com/file/d/1Sp_5bv6eGnu9nS76_qbfgF9vce-a7foc/view?usp=sharing)
- [mechanical mate: belt+pully](https://drive.google.com/file/d/1mSaCNOARRRefY3WBKz_m-PttF0iSjpmX/view?usp=sharing)
- [exploded and collapsed views](https://mediastream.brighton.ac.uk/Play/17761)
- [animations: rotate, explode, collapse](https://mediastream.brighton.ac.uk/Play/17763)

## Drawings
- note differences between parts and assemblies (see above for fuller description)
- [good exercises to help understand technical drawings](https://drive.google.com/open?id=1MHMAI9HZpqp_m3xgFLtKBn179Hc6kqDi)
- [solidworks A4 drawing template](https://drive.google.com/open?id=1oSnJt-BSTECa_LRzgIEuoPoB3L85mbhN)
- [1st or 3rd angle projection?](https://youtu.be/_wDpN6Zi1hE)
