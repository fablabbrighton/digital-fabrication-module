---
layout: page
title:  "Week 2: Computer-Aided Design"
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
1. Parametric: everything is driven by numbers (length, diameter, thickness, colour, etc). 
2. Feature-based: geometry is created with features
3. Associative: parts, assembles, drawings are linked - a change in one will filter to all

SW can do: FEA, CFD, motion analysis, electronic wiring, lots more!

Student licences- £6 for a USB from computer store, 1st Floor Watts Building. Renew at the start of each academic year. 

[Certification exams:](https://www.solidworks.com/sw/support/mcad-certification-programs.htm) we will provide these: TBA

## Resources:
- Start with these.....Help menu > tutorials (Lesson1: parts, Lesson2: Assembles, Lesson3: drawings) - these are excellent, make notes, observe everything and master them.
- [lesson 1: parts video](https://www.youtube.com/watch?v=HKSo99hGDd4)
- [lesson 2: assemblies video](https://www.youtube.com/watch?v=yGvZ3Jly1mI)
- [lesson 3: drawings video](https://www.youtube.com/watch?v=lX85kgun8sE)
- use the help (online also)
- Grabcad/Thingyverse/etc (filter for Solidworks models). 
- any existing models to reverse engineer
- Lynda.com (for UoB: www.brighton.ac.uk/lynda) - Solidworks 20XX essentials. 
- sketching exercises
- part modelling exercises

## Layout:
- [user interface](http://help.solidworks.com/2018/english/SolidWorks/sldworks/c_user_interface_overview.htm?id=3142cd59ed8f4abd874df330c405866b#Pg0)

Units: see bottom right hand corner (use millimeters!)

## Navigation:
MIDDLE DOES EVERYTHING! 
- zoom: scroll middle 
- rotate: hold middle 
- pan: hold middle + CTRL

## File types: (IMAGE OF EACH)
1. [Parts: as it would be manufactured](https://i.ytimg.com/vi/zNDwvsU5Dko/maxresdefault.jpg)
2. [Assemblies: a collection of parts (and/or of other sub-assemblies)](https://www.javelin-tech.com/blog/wp-content/uploads/2017/07/solidworks-rigid-subassembly-780x417.jpg)
3. Drawings: orthographic of [parts (with dimensions)](https://i.ytimg.com/vi/k_45Xr3wHtk/maxresdefault.jpg) and [assemblies (with NO dimensions, with balloons + bill of materials (BOM))](https://ayoqq.org/images/assembly-drawing-engineering-2.png)....or [both](https://ayoqq.org/images/solidworks-drawing-solidworks-assembly-13.jpg)

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

## Useful tools:
- [toolbox (nuts, bolts, gears etc)](http://help.solidworks.com/2018/english/solidworks/toolbox/t_toolbox_activating_add_ins.htm)
- [Traceparts CAD models](https://www.traceparts.com/en)
- also Grabcad/Thingyverse/etc
- [solidworks A4 drawing template](https://drive.google.com/open?id=1oSnJt-BSTECa_LRzgIEuoPoB3L85mbhN)
- [1st or 3rd angle projection?](https://youtu.be/_wDpN6Zi1hE)

## Assignment

Design a 100x100mm tile part (SW or Fusion), colour it, and assemble 9 of them as a pattern of 3x3. Create a drawing (A4 or A3) of your tile part with sufficient detail for it to be manufactured by someone else. 

### What do I need to do to pass?

* Use parametric CAD software to design a tile part that is dimensioned correctly
* Create a simple 2D drawing of your tile with key dimensions and also include part details in the title block
* Document all your work on your student blog, with photos/screengrabs and videos to show what you did, what went wrong, and how you fixed it. Make sure you include a final hero shot of the final outcomes. Cite external sources where you have used someone else’s work.

### Extra credit 

Design a male mould tool to make female mould tool, show as exploded assembly of the 3 parts (male mould tool + female mould tool + part)
