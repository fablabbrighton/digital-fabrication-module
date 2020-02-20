---
layout: page
title:  "3D Fabrication: 3D Printer"
date:   2020-01-02
author: Andrew Sleigh
---

Additive manufacturing in plastic.

<!--more-->

## 3D Printer

* Process: FDM (Fused Deposition Modelling: i.e. hot, layers)
* Materials: **PLA**, ABS, TPU, Nylon, PET

## Safety

* Materials: only PLA (no fumes)
* Heat: Hot end approx 200&deg;C, bed approx 40–70&deg;C
* Motors: kep your fingers out of the way
* Unattended prints: prints go wrong; you must be in the room and keep an eye on the printer. 

## Constraints / Design rules

* Printing layer by layer / supports, overhangs
* Resolution
* Aesthetic limitations

Anti-constraints:
* Pre-assembled parts / mechanisms
* Programmatic customisation
* Affordable one-offs (no tooling)

* Follow some simple '[design rules](https://www.3dhubs.com/knowledge-base/key-design-considerations-3d-printing)'

## Workflow

### 1. CAD

Design your 3D model and save as an `.STL` file

Software:
* Fusion 360
* Solidworks

Or download a model as STL (e.g. Thingiverse)

### 2. Slice

* 'Slice' the model into layers to generate tools paths.
* Configure settings for your printer and model
* Inspect the preview and adjust the 'printing strategy' ([Here's a video](https://www.youtube.com/watch?v=gvUmeJ3r58A) showing how to view the layers and toolpath in Cura.)
* Save file as `.GCODE` onto SD card

Software: 
* Cura
* Slic3r
* [Simplify3d](https://www.simplify3d.com/)

### 3. Print
* Load filament into printer
* Check bed 
* Print file from SD card
* Monitor while printing, especially first few layers. Be careful of tall models with overhangs


### 4. (Repeat)

* What worked, what didn't?
* Do you need to change your design, or just your print settings?

### 5. Finishing / Assembly

* Often much easier to print a model in 2 parts and assemble
* Surface finishing
* Bodging



[**3D printing**](http://academy.cba.mit.edu/classes/scanning_printing/index.html "3d printing")

*   is an exciting new area [making lots of interesting things](https://www.google.com/search?q=3d+printing+examples&source=lnms&tbm=isch&sa=X&ved=0ahUKEwjfxeWJwf3gAhU0XRUIHVC1BgsQ_AUIDigB&biw=1420&bih=697) but the hype is too much!
*   is additive manufacturing, like lego!
*   requires [support material (in most cases)](https://www.google.com/search?biw=1420&bih=697&tbm=isch&sa=1&ei=ah-IXIzqFoPRrgTwx6mwCA&q=3d+printing+support+material&oq=3d+printing+support+material&gs_l=img.3..0j0i24l3.74515.76108..76253...0.0..0.189.1550.13j4......1....1..gws-wiz-img.......0i67j0i8i30j0i30.7EnP8jt2LP4)
*   creates inherent weaknesses [or variable properties](https://www.ncbi.nlm.nih.gov/pubmed/29904165) between layers of parts
*   the challenge is creating/using [design tools](http://eprints.brighton.ac.uk/14489/1/template_CGIconf_CameraReadyFINAL.pdf) to support the geometric freedom 3DP affords - there are no straight lines in nature!
*   our 3DP centre in AEB mostly prints in ABS/PLA/flexible
*   our machines: <span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">[raise3d n2 plus](https://technologyoutlet.co.uk/collections/raise-3d/products/raise3d-pro2-plus-3d-printer), </span><span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">[bigbuilder](https://www.3dhubs.com/3d-printers/big-builder-dual-feed-extruder), </span>[Fusion3](https://www.fusion3design.com/), <span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">[Form2,](https://formlabs.com/3d-printers/form-2/) </span><span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">[Fortus 250mc](https://www.3dhubs.com/3d-printers/fortus-250mc), </span>[Wanhao](https://www.amazon.co.uk/Wanhao-5S-Duplicator-3D-Printer/dp/B00OUOM9GU)<span style="color: #1f497d; font-family: Calibri, sans-serif; font-size: 11pt;"> [duplicator 5s](https://www.amazon.co.uk/Wanhao-5S-Duplicator-3D-Printer/dp/B00OUOM9GU), </span>[<span style="font-size: 11.0pt; font-family: 'Calibri',sans-serif; color: #1f497d;">Makerbots replicator 2x</span>](https://www.tritech3d.co.uk/manufacturer/makerbot-3d-printers/?gclid=CjwKCAiAo8jgBRAVEiwAJUXKqMIWVOSolkJdXcF9ep0apS4pJ1p-BghMfgEbxOuL71y4QoMzO1tq3BoCzTIQAvD_BwE)
*  fablab machine: [creality CR-10](https://all3dp.com/1/creality-cr-10-3d-printer-review-worth-the-hype/)



*   [.stl files](https://all3dp.com/what-is-stl-file-format-extension-3d-printing/)
*   [finishing 3dp parts](https://www.fictiv.com/hwg/fabricate/ultimate-guide-to-finishing-3d-printed-parts)



### Software

(Fusion 360)
Cura



## Assignment

Print a pre-designed 3D object 
Consider time to fabricate

## Prep for next week

Install Fusion 360
Watch tutorials
Design something
