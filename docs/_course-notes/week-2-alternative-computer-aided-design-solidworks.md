---
layout: page
title:  "Week 2: Computer-Aided Design (Solidworks)"
date:   2018-2-5
author: Derek Covill
---

Introducing parametric modelling.

<!--more-->

## Background information on CAD

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

## Early part challenge:
- create a 6-sided die (10x10x10mm, R1mm fillets on all faces, D2mm holes 0.5mm deep (opposing sides add up to 7)
- all details must be dimensioned fully
- approach this in different ways, aim to do it as fast as you can
- record < 1min, excellent < 5min, ok < 15min
- [2019 leaderboard](https://docs.google.com/document/d/1r5j0Bj-RQjewX0iajl6O0TMxy5sYbaCDed5bEuyTX-0/edit?usp=sharing)
- [example die part file to download](https://drive.google.com/open?id=1zCTDj-7bnFJ6TkA2ZZHRS2rKuS0ElQmB)

## Second part challenge:
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

## Assembly challenge
- [download this .zip folder and unzip it](https://drive.google.com/file/d/1jH7XwE33P4RMQmV67FFxBVaTm9ZSLlcs/view?usp=sharing)
- open the "plunger.asm" assembly file
- look at how the parts move
- [here is an assembly drawing to act as a guide](https://drive.google.com/file/d/112c3L1f3jn8uLBRjYEZWmU9sTZMI33C_/view?usp=sharing)
- the challenge: recreate this assembly in a new assembly file. Create an exploded view and animate the explode/collapse.
- bonus: position the link plunger so that it is 15degrees to the horizontal. This will lock the assembly so it won't move. 

## Drawings
- Help menu > tutorials (Lesson3: drawings)
- [lesson 3: drawings video](https://www.youtube.com/watch?v=lX85kgun8sE)
- advanced tutorials: - Help menu > tutorials (all) > Advanced drawings (a.Drawing views, b. Detailing, c. Assembly Drawing views)
- orthographic drawings of parts (with dimensions). Note that there should be sufficient detail and dimensions for the part to be manufactured. Drawings should be checked by others. 
![simple part drw]({{ site.baseurl }}/assets/simple-2d-drw.jpg)

- assembly drawings have NO dimensions, but they do have balloons and include bill of materials (BOM)
![simple assembly drw]({{ site.baseurl }}/assets/simple-assembly-drw.jpg)

- you can also combine both types of drawings into a single drawing, but this is not advised. [both-part-assembly-drw-combined](https://ayoqq.org/images/solidworks-drawing-solidworks-assembly-13.jpg). 
- [introduction to technical drawing](https://ocw.mit.edu/courses/mechanical-engineering/2-007-design-and-manufacturing-i-spring-2009/related-resources/drawing_and_sketching/)
- [types of views](https://knowledge.autodesk.com/support/inventor-products/getting-started/caas/CloudHelp/cloudhelp/2019/ENU/Inventor-Help/files/GUID-C53DAB48-BA5F-4377-842D-BB8F3E5962A0-htm.html)
- [BS 8888:2017 –Technical product documentation and specification](https://www.bsigroup.com/en-GB/about-bsi/media-centre/press-releases/2017/february/UKs-national-standard-for-engineering-drawings-revised/)
- include appropriate tolerances [simple tolerances drw]({{ site.baseurl }}/assets/Pololu-Stepper-Motor-drawing-tolerance.jpg)
- base tolerances on [manufacturing capability charts](http://capitadiscovery.co.uk/brighton-ac/items/1377842)
- [limits and fits tolerances for holes and shafts]({{ site.baseurl }}/assets/iso-fits-hole.jpg)
- [use the solidworks A4 drawing template](https://drive.google.com/open?id=1oSnJt-BSTECa_LRzgIEuoPoB3L85mbhN)
- [1st (roll) or 3rd (slide) angle projection video](https://youtu.be/_wDpN6Zi1hE)

## Part drawing challenge 1
- [here are some good exercises to help understand technical drawings](https://drive.google.com/open?id=1MHMAI9HZpqp_m3xgFLtKBn179Hc6kqDi)
- pick one of these, create the part then create the drawing for this part

## Part drawing challenge 2
- Lego part challenge

## Assembly drawing challenge
- GrabCAD assembly
