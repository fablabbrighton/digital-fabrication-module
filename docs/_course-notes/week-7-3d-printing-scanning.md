---
layout: page
title:  "Week 7: 3D printing and scanning"
date:   2018-3-5
author: Derek Covill
---

Introducing 3D printing and scanning.

<!--more-->


## Prep for this week's class

Watch the corresponding Fab Academy lecture. We'll be covering part of this content. 

* Fab Academy lecture notes: <http://academy.cba.mit.edu/classes/scanning_printing/index.html>  
* [Lecture from 2018](http://fab.academany.org/2018/lectures/fab-20180221.html)

## Baseline 

Who has:

* 3d printed something?
* laser scanned something?

[**3D printing**](http://academy.cba.mit.edu/classes/scanning_printing/index.html "3d printing")

*   is an exciting new area, but the hype is too much
*   is additive manufacturing
*   requires support material
*   creates inherent weaknesses between layers of parts
*   the challenge is creating/using [design tools](http://eprints.brighton.ac.uk/14489/1/template_CGIconf_CameraReadyFINAL.pdf) to support the geometric freedom 3DP affords - there are no straight lines in nature!
*   our 3DP centre in AEB
*   our machines: <span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">[raise3d n2 plus](https://technologyoutlet.co.uk/collections/raise-3d/products/raise3d-pro2-plus-3d-printer), </span><span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">[bigbuilder](https://www.3dhubs.com/3d-printers/big-builder-dual-feed-extruder), </span>[Fusion3](https://www.fusion3design.com/), <span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">[Form2,](https://formlabs.com/3d-printers/form-2/) </span><span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">[Fortus 250mc](https://www.3dhubs.com/3d-printers/fortus-250mc), </span>[Wanhao](https://www.amazon.co.uk/Wanhao-5S-Duplicator-3D-Printer/dp/B00OUOM9GU)<span style="color: #1f497d; font-family: Calibri, sans-serif; font-size: 11pt;"> [duplicator 5s](https://www.amazon.co.uk/Wanhao-5S-Duplicator-3D-Printer/dp/B00OUOM9GU), </span>[<span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">Makerbots replicator 2x</span>](https://www.tritech3d.co.uk/manufacturer/makerbot-3d-printers/?gclid=CjwKCAiAo8jgBRAVEiwAJUXKqMIWVOSolkJdXcF9ep0apS4pJ1p-BghMfgEbxOuL71y4QoMzO1tq3BoCzTIQAvD_BwE)
*  fablab machine: [creality CR-10](https://all3dp.com/1/creality-cr-10-3d-printer-review-worth-the-hype/)

*   good software: [simplify3d](https://www.simplify3d.com/) to slice the stls <span style="font-size: 13px;">and</span> create <span style="font-size: 13px;">the</span> gcode<span style="font-size: 13px;">.</span>
*  free software to generate toolpath for 3D printers (can animate in layer view): [Ultimaker Cura](https://ultimaker.com/en/resources/51943-installation-ultimaker-cura)

*   [design rules](https://www.3dhubs.com/knowledge-base/key-design-considerations-3d-printing)
*   [.stl files](https://all3dp.com/what-is-stl-file-format-extension-3d-printing/)
*   [finishing 3dp parts](https://www.fictiv.com/hwg/fabricate/ultimate-guide-to-finishing-3d-printed-parts)

*   assignment
    *   individual: 3d print your mouse from scan, or scan+CAD. Submit file by Friday 14th 5pm into XE404 > Assessments > Mouse STL file submission area. Note: if you don't get it finished, we can print it after xmas break. 
    *   group: make the [documentation](https://docs.google.com/document/d/15gcyV69IcsJk2qgAGhEzvlpLC0jyFJMrBUhrpJumlW8/edit?usp=sharing) awesome

**laser scanning**

*   [photogrammetry vs 3D scanning](https://peel-3d.com/blogs/news/7-things-you-should-know-about-photogrammetry-vs-3d-scanning "photo G vs 3D scanning")
*   [our scanner](https://structure.io/ "Occipital Structure Scanner")
*   [meshmixer](http://www.meshmixer.com/ "meshmixer")
    *   typical process: edit>transform(rotate), close cracks, analysis>inspector,smooth, plane-cut, edit>make solid. Have a play!
    *   note: can also bring mesh into Rhino, use 'project curves' to create profile curves on the mesh, then use these to create Rhino surfaces that are better quality than the smoothed mesh. You can also add CAD into the mesh (e.g. scroll wheel) to add extra detail. Have a play!
    *   [tutorial from my aussie friend](https://www.youtube.com/watch?v=C9VDKb3W4qA "meshmi tutorial 1")
    *   [tutorial 2](https://all3dp.com/meshmixer-tutorial/ "meshmixer tutorial2")
    *   [tutorial 3](https://i.materialise.com/blog/en/3d-printing-with-meshmixer-a-beginner-friendly-introduction-to-3d-sculpting-and-combining-meshes/ "meshmixer tutorial3")
    *   [design](http://www.meshmixer.com/design.html "meshmixer design")
*   [meshlab](http://www.meshlab.net/ "meshlab")
    *   [remeshing and meshlab - butterfly subdivision](https://youtu.be/LeuX963jpn8 "remeshing and meshlab")

## Assignment
- design 50x50x5mm tile in CAD (max height 20mm) making sure you apply appropriate design rules. Save your model as .stl file (with appropriate resolution based on 0.1mm layer height). Submit your .stl file to the assessment area in this module on Studentcentral by 5pm on Friday 29th March and we will print this over easter. 
- load your .stl file into the Ultimaker Cura software and animate the printing process (layer view, press play!). Record an accelerated version of this (or just a short period of it) using a screen recorder or on your phone and embed the video onto your blog. 

### What do I need to do to pass?
- submit a .stl file of a tile (or other small part) that you have designed and include this into your blog. 

### Extra credit 
- scan a physical object (e.g. computer mouse)
- tidy up the scanned mesh in meshmixer
- use a cad package (e.g. Rhino, Fusion) to project curves onto the scanned mesh to create tidy cad geometry
- save as .stl file and submit

### For the super keen
- create a cad model of a part that can not made using any other single technology (subtractive, casting, moulding). OR create a design of an object that can be cleverly made/assembled without support material. 
- submit this .stl file for printing
