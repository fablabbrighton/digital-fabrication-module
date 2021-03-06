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
### Rules
- make it clear!
- use only enough views as are necessary
- don't duplicate dimensions
- make dimensions measurable (using ruler, calipers, micrometer etc)
- don't cross dimensions
- space dimensions consistently
- don't place dimensions on a part
- make sure the title block is complete
- use sans serif fonts only (ideally use CAPS)

### Tutorial
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

## Part drawing challenge
- [here are some good exercises to help understand technical drawings](https://drive.google.com/open?id=1MHMAI9HZpqp_m3xgFLtKBn179Hc6kqDi)
- pick one of these, create the part then create a complete drawing for this part (assume one square = 10mm)
- use the template provided above
- include all dimensions required to make the part
- include a complete title block
- assume that it is machined using a CNC milling machine and then specify the appropriate tolerances using the manufacturing process capability charts above

## Assembly drawing challenge
- find an interesting assembly in GrabCAD (make sure it's a Solidworks assembly!) and download it
- unzip the folder with all the files
- make a complete assembly drawing of the main assembly
- use the template provided above
- include a complete title block
- include baloons for all parts
- include a complete/appropriate BOM (note that you may need to make adjustments to part names or other details)

## Advanced part drawing challenge for homework
- Lego part challenge: download the [lego solidworks part here]({{ site.baseurl }}/assets/lego.SLDPRT)
![lego solidworks part]({{ site.baseurl }}/assets/lego.jpg)
- create a part drawing of this lego brick
- use the template provided above
- include all dimensions required to make the part
- include a complete title block
- note the requirements for this to be a 
- assume that it is injection moulded from ABS and then specify the appropriate tolerances using the manufacturing process capability charts above
- assume that the bosses of the lego brick need to be a 'press fit' with the underside of the next brick, using a [H7/p6 tolerance](https://en.wikipedia.org/wiki/Engineering_fit) which assumes H7 (hole) tolerance range = +0.000 mm to +0.025 mm, and p6 (shaft) tolerance range = +0.042 mm to +0.026 mm
- note...this is challenging :0)

## More features in Solidworks
- features: extrude, hole wizard, mirror, pattern, shell, fillet, revolve, sweep, loft, split
![reamer solidworks part]({{ site.baseurl }}/assets/reamer.JPG)
- [reamer part with many features]({{ site.baseurl }}/assets/reamer.SLDPRT)
- Help menu > tutorials (All) > Revolves and Sweeps, Lofts, Patterns, Fillets)

## Solidworks part features exam! (1 hour)
1.	Make a donut (overall diameter 100mm, section diameter 20mm) using a revolve (10 marks)
2.	Put a M5 countersunk hole through the donut (in axial direction) (5 marks)
3.	Pattern this hole so that there are 5 of them spaced around the donut (5 marks) 
4.	Take a measurement of the cross sectional area of one cut through the donut where an M5 hole is (5 marks)
5.	In the same part make the same donut (no holes this time) again using a sweep (position it next to the existing feature) (10 marks)
6. Now make it using a loft! Again, position it next to the existing parts (15 marks)
- Score out of 50? (Pass >= 25, merit >=35, distinction >= 45)
- [here's the finished part with the donuts!]({{ site.baseurl }}/assets/donuts-yum.SLDPRT)
- [here's the section view results]({{ site.baseurl }}/assets/section-properties-donut.PNG)

## 3D sketching in solidworks
- first a little warmup! let's make this [2D sketch](https://drive.google.com/file/d/1ajGt5Q1zw7DI038VV2AqcWIN0Atd1zLh/view?usp=sharing), and then make [this solid part](https://drive.google.com/open?id=1Ke5bJkanrOG-HjR7hoECaNf1iZaSUutg)
- if you like that sketching exercise, [here is 99 more!](https://drive.google.com/open?id=1kcsn3ghW-dgm7xf_htp9wL9p7MROS2PX)
- until now we've avoided 3D sketches because they can limit the ability to do features (e.g. revolve, loft)
- but they can also open up new ways to create geometry
- they work by creating a sketch that moves between sketching planes (e.g xy, yz, xz and any planes parallel to them) - and this is done by pressing TAB
- you can then draw lines in and out of these planes as we'll see in this example
- [3d-sketched-rack-part](https://drive.google.com/file/d/1TfvRNJ6R4RgUsAJ-7HKiaMVOm0jbPXOc/view?usp=sharing)
- this example is also done as part of the tutorial in Help menu > tutorials > 3d sketching

## Certified SOLIDWORKS Associate (CSWA) exam
- let's look at the [Certified SOLIDWORKS Associate (CSWA) exam](https://www.solidworks.com/sw/support/mcad-certification-programs.htm)
- and [here is the sample exam - note it takes 3 hours](https://www.solidworks.com/sw/docs/CSWASampleExam.ZIP)
- let's have a go!
- [preparing for the CSWA exam](https://www.youtube.com/watch?v=6cAx0KCXSYo&list=PLE5C6B3135D7D277F)
- [Q3-sample-exam-answer-part](https://drive.google.com/file/d/1ME0vQXX9qqYZGTJVDBT1684ww1vSxfbI/view?usp=sharing)
- [Q7-sample-exam-partial-answer-assembly](https://drive.google.com/file/d/1XQIkZ6ZvrbmI68ASbxJFHmIXSffiRXH4/view?usp=sharing)
