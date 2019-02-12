---
layout: page
title:  "Week 2: Computer-Aided Design (Fusion 360)"
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

# Fusion 360 (PC+Mac compatible, cloud based)
is...
1. Parametric: everything is driven by numbers (length, diameter, thickness, colour, etc). 
2. Feature-based: geometry is created with features
3. Associative: parts, assembles, drawings are linked - a change in one will filter to all

Fusion 360 can do: FEA, animation, CAM, link with Eagle (electronics design), lots more!

[Download and use for free](https://www.autodesk.co.uk/products/fusion-360/overview)

## Introductory videos:
Start with these.....
- [part 1: box component](https://www.youtube.com/watch?v=A5bc9c3S12g)
- [part 2: lid component and assembly](https://www.youtube.com/watch?v=HXRMzJWo0-Q)
- [part 3: complex lid detail + McMaster Carr-toolbox](https://www.youtube.com/watch?v=zS8dYA_Iluc)
- [part 4: drawings](https://www.youtube.com/watch?v=uinJ2I_SgKI)
- [part 5: adding colour to bodies/surfaces](https://www.youtube.com/watch?v=oD0d3lAiMC4)

## Other resources:
- [another good introductory video](https://www.youtube.com/watch?v=VbSkwvZyU_0)

- [Autodesk videos](https://www.autodesk.co.uk/products/fusion-360/get-started)
- Lynda videos how in LindedIn learning, access these through [https://www.brighton.ac.uk/lynda](https://www.brighton.ac.uk/lynda)
- [modelling shortcuts](https://www.autodesk.com/shortcuts/fusion-360#modeling)

- [Fusion 360 gallery of models](https://gallery.autodesk.com/fusion360)
- Grabcad/Thingyverse/etc (filter for Fusion 360 models). 
- any existing models to reverse engineer

## Some material to practice on:
- [sketching exercises](https://drive.google.com/open?id=1kcsn3ghW-dgm7xf_htp9wL9p7MROS2PX)
- [part modelling exercises](https://drive.google.com/open?id=1fmFIsjV-P9DPdEKxaB_PEqnUaqnMnYti)

## Layout:
- [user interface](http://help.autodesk.com/view/fusion360/ENU/?guid=GUID-E647CA56-7187-406A-ACE4-EAC59914FAE4&utm_medium=email&utm_source=invite&utm_campaign=amer-edu-aex-fusion-360-nurture-stream-edms&utm_id=672747&mktvar002=672747)

Units: see bottom right hand corner (use millimeters!)

## Navigation:
Use mouse shortcuts to zoom in and out, pan, and orbit the view of the model.
- Zoom in and out: Scroll the mouse wheel forward and backward.
- Pan: Left-click and hold, then drag.
- Orbit: Hold the Shift key, click and hold the middle mouse button, then drag.
- Zoom Extents: Double-click the middle mouse button.

[more on navigation](http://help.autodesk.com/view/fusion360/ENU/?guid=GUID-7B742BB2-65B3-4ADA-9B11-9D57E1E31292)

## File models:
1. [Components: as it would be manufactured](https://i.ytimg.com/vi/zNDwvsU5Dko/maxresdefault.jpg)
2. [Assemblies: a collection of components put together (and/or of other sub-assemblies)](https://www.javelin-tech.com/blog/wp-content/uploads/2017/07/solidworks-rigid-subassembly-780x417.jpg)
3. Drawings: orthographic of [parts (with dimensions)](https://i.ytimg.com/vi/k_45Xr3wHtk/maxresdefault.jpg) and [assemblies (with NO dimensions, with balloons + bill of materials (BOM))](https://ayoqq.org/images/assembly-drawing-engineering-2.png)....or [both](https://ayoqq.org/images/solidworks-drawing-solidworks-assembly-13.jpg)

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

### Sketch tools:
- extend
- offset
- trim
- fillet
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
- [2019 leaderboard](https://docs.google.com/document/d/1-FwDeOOHf4sGzqut6M7kvIdFJoBKI5EFxtkPCBo_XeE/edit?usp=sharing)

- [here's an example completed component](https://a360.co/2Gm9naL)

## Useful tools:
- [toolbox (nuts, bolts, gears etc)](http://help.solidworks.com/2018/english/solidworks/toolbox/t_toolbox_activating_add_ins.htm)
- [Traceparts CAD models](https://www.traceparts.com/en)
- also Grabcad/Thingyverse/etc
- [1st or 3rd angle projection?](https://youtu.be/_wDpN6Zi1hE)
- [technical drawing guide](https://ocw.mit.edu/courses/mechanical-engineering/2-007-design-and-manufacturing-i-spring-2009/related-resources/drawing_and_sketching/)

## Assignment

Design a 100x100mm tile part (SW or Fusion), colour it, and assemble 9 of them as a pattern of 3x3. Create a drawing (A4 or A3) of your tile part with sufficient detail for it to be manufactured by someone else. 

### What do I need to do to pass?

* Use parametric CAD software to design a tile part that is dimensioned correctly
* Create a simple 2D drawing of your tile with key dimensions and also include part details in the title block
* Document all your work on your student blog, with photos/screengrabs and videos to show what you did, what went wrong, and how you fixed it. Make sure you include a final hero shot of the final outcomes. Cite external sources where you have used someone else’s work.

### Extra credit 

Design a male mould tool to make female mould tool, show as exploded assembly of the 3 parts (male mould tool + female mould tool + part)
