---
layout: page
title:  "Guide: Hello Soldering board"
date:   2019-02-22
author: Andrew Sleigh
---

How does the board work, and how to solder the components

<!--more-->

## What is it?

Hello Soldering is a very simple PCB that allws novice solderers to practice their craft – specifically with 1206-size SMD components

It consists of 10 SMD LEDs in an array of 5 parallel lines (2 LEDs in series in each line). Each line also has a current-limiting resistor.

Power is provided by 2 large pads which can be hooked up to a power supply with crocodile clips, or could accept headers for other kinds of connections.

The pads are spaced and sized in gradations of difficulty to allow for improvement in skill. 


## Circuit design

![Hello Soldering]({{ site.baseurl }}/assets/soldering-practice-board-V2-diagram-01.png)



## BOM (Bill of materials)

Values are calculated on the basis of a 5V DC supply.

5 x Red 1206 SMD LEDs
5 x Green 1206 SMD LEDs
5 x 100 Ohm 1206 SMD Resistors

(Actually, 75 Ohm resistors would be more appropriate, but 100 Ohm resistors are commonly available in Fablabs, and are close enough for this job)


## Milled board

<span class="wip">WIP</span>

## Stuffed board

<span class="wip">WIP</span>

## Powered board

<span class="wip">WIP</span>


## Improvements

Resistors are the most abundant component in the lab, so a board with more resistors would be more economical and drain fewer resources

It would be good to include some IC components, such as an SMD 555 timer, which would also allow for flashing LEDs

A greater variety of components would also allow for some learning of basic principles of electronics.



## Files

<span class="wip">WIP</span>

Eagle files
PNGs for milling (inc batch milling layup)

