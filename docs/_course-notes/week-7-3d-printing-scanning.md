---
layout: page
title:  "Week 7: 3D printing and scanning"
date:   2018-3-5
author: Derek Covill
---

Part 1: Introducing 3D printing with tour of facilities and demo of AEB.
Part 2: Introducting laser scanning with demo activity.

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

*   is an exciting new area [making lots of interesting things](https://www.google.com/search?q=3d+printing+examples&source=lnms&tbm=isch&sa=X&ved=0ahUKEwjfxeWJwf3gAhU0XRUIHVC1BgsQ_AUIDigB&biw=1420&bih=697) but the hype is too much!
*   is additive manufacturing, like lego!
*   requires [support material (in most cases)](https://www.google.com/search?biw=1420&bih=697&tbm=isch&sa=1&ei=ah-IXIzqFoPRrgTwx6mwCA&q=3d+printing+support+material&oq=3d+printing+support+material&gs_l=img.3..0j0i24l3.74515.76108..76253...0.0..0.189.1550.13j4......1....1..gws-wiz-img.......0i67j0i8i30j0i30.7EnP8jt2LP4)
*   creates inherent weaknesses [or variable properties](https://www.ncbi.nlm.nih.gov/pubmed/29904165) between layers of parts
*   the challenge is creating/using [design tools](http://eprints.brighton.ac.uk/14489/1/template_CGIconf_CameraReadyFINAL.pdf) to support the geometric freedom 3DP affords - there are no straight lines in nature!
*   our 3DP centre in AEB mostly prints in ABS/PLA/flexible
*   our machines: <span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">[raise3d n2 plus](https://technologyoutlet.co.uk/collections/raise-3d/products/raise3d-pro2-plus-3d-printer), </span><span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">[bigbuilder](https://www.3dhubs.com/3d-printers/big-builder-dual-feed-extruder), </span>[Fusion3](https://www.fusion3design.com/), <span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">[Form2,](https://formlabs.com/3d-printers/form-2/) </span><span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">[Fortus 250mc](https://www.3dhubs.com/3d-printers/fortus-250mc), </span>[Wanhao](https://www.amazon.co.uk/Wanhao-5S-Duplicator-3D-Printer/dp/B00OUOM9GU)<span style="color: #1f497d; font-family: Calibri, sans-serif; font-size: 11pt;"> [duplicator 5s](https://www.amazon.co.uk/Wanhao-5S-Duplicator-3D-Printer/dp/B00OUOM9GU), </span>[<span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">Makerbots replicator 2x</span>](https://www.tritech3d.co.uk/manufacturer/makerbot-3d-printers/?gclid=CjwKCAiAo8jgBRAVEiwAJUXKqMIWVOSolkJdXcF9ep0apS4pJ1p-BghMfgEbxOuL71y4QoMzO1tq3BoCzTIQAvD_BwE)
*  fablab machine: [creality CR-10](https://all3dp.com/1/creality-cr-10-3d-printer-review-worth-the-hype/)

*   good software: [simplify3d](https://www.simplify3d.com/) to slice the stls <span style="font-size: 13px;">and</span> create <span style="font-size: 13px;">the</span> gcode<span style="font-size: 13px;">.</span>
*  free software to generate toolpath for 3D printers (can animate in layer view): [Ultimaker Cura](https://ultimaker.com/en/resources/51943-installation-ultimaker-cura). And [here's a video](https://www.youtube.com/watch?v=gvUmeJ3r58A) showing how to view the layers and toopath in cura. 

*   [design rules](https://www.3dhubs.com/knowledge-base/key-design-considerations-3d-printing)
*   [.stl files](https://all3dp.com/what-is-stl-file-format-extension-3d-printing/)
*   [finishing 3dp parts](https://www.fictiv.com/hwg/fabricate/ultimate-guide-to-finishing-3d-printed-parts)

**laser scanning**

*   [photogrammetry vs 3D scanning](https://peel-3d.com/blogs/news/7-things-you-should-know-about-photogrammetry-vs-3d-scanning "photo G vs 3D scanning")
*   [our scanner](https://structure.io/ "Occipital Structure Scanner"), and [how it works](https://support.canvas.io/article/7-how-does-structure-sensor-work)
*   [meshmixer](http://www.meshmixer.com/ "meshmixer")
    *   typical process: edit>transform(rotate), close cracks, analysis>inspector, smooth, plane-cut, edit>make solid. Have a play!
    *   note: can also bring mesh into Rhino, use 'project curves' to create profile curves on the mesh, then use these to create Rhino surfaces that are better quality than the smoothed mesh. You can also add CAD into the mesh (e.g. scroll wheel) to add extra detail. Have a play!
    *   [tutorial from my aussie friend](https://www.youtube.com/watch?v=C9VDKb3W4qA "meshmi tutorial 1")
    *   [tutorial 2](https://all3dp.com/meshmixer-tutorial/ "meshmixer tutorial2")
    *   [tutorial 3](https://i.materialise.com/blog/en/3d-printing-with-meshmixer-a-beginner-friendly-introduction-to-3d-sculpting-and-combining-meshes/ "meshmixer tutorial3")
    *   [design](http://www.meshmixer.com/design.html "meshmixer design")
*   [meshlab](http://www.meshlab.net/ "meshlab")
    *   [remeshing and meshlab - butterfly subdivision](https://youtu.be/LeuX963jpn8 "remeshing and meshlab")

## Assignment option 1
- design 50x50x5mm tile in CAD (max height 20mm) making sure you apply appropriate design rules. Save your model as .stl file (with appropriate resolution based on 0.1mm layer height). Submit your .stl file to the assessment area in this module on Studentcentral by 5pm on Friday 29th March and we will print this over easter. 
- load your .stl file into the Ultimaker Cura software and animate the printing process (layer view, press play or [here's a tutorial video](https://www.youtube.com/watch?v=gvUmeJ3r58A) showing how to view the layers and toopath in cura. ). Record an accelerated version of this (or just a short period of it) using a screen recorder or on your phone and embed the video onto your blog.

## Assignment option 2
- laser scan a small (e.g. hairdryer sized) object. Load the scan into meshmixer and repair/tidy/knit it and document this on your blog.

### What do I need to do to pass?
- create an .stl file of a small tile (or other small part) that you have designed and document this on your blog 
- OR...
- laser scan (or use photogrammetry) an object, open the scan in meshmixer and repair/tidy/knit it and document this on your blog.

### Extra credit for the 3D printing assignment
- create a cad model of a part that can not made using any other single technology (subtractive, casting, moulding). OR create a design of an object that can be cleverly made/assembled without support material. 
- submit this .stl file for printing and document this process on your blog

### Extra credit for the scanning assignment
- use a cad package (e.g. Rhino, Fusion) to project curves onto the scanned mesh to create tidy cad geometry
- save as .stl file and submit and document this on your blog
