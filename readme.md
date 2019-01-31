# Readme

This project contains course notes, code and design files for a module in digital fabrication methods taught at the University of Brighton.

## Published version

A live version of this content is published at: **https://fablabbrighton.github.io/digital-fabrication-module/**

This is published using Github Pages from the source markdown files in the [`/docs`](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/docs) folder of this repo.

## How to contribute

Content is stored in a structure to support publishing via Jekyll/Github Pages to a [flat HTML website](https://fablabbrighton.github.io/digital-fabrication-module/).


### Site structure

If you'd like to contribute, or use the content, most of the course content is located in the [`/docs`](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/docs) folder.

Course notes for each week are in [`/docs/_course-notes`](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/docs/_course-notes)

There are also folders for special projects and howto guides, such as:

* [`/docs/_diy-arduino`](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/docs/_diy-arduino) – experimenting with making a simple arduino board in the lab
* [`/docs/_guides`](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/docs/_guides) – howto guides for common processes in the lab
* [`/docs/_colophon`](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/docs/_colophon) – how the site is made

Design files and code examples are in their own folders at the root level: [`/3d-models`](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/3d-models), [`/arduino-code`](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/arduino-code), [`/board-designs`](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/board-designs), etc.

### Adding a new course page

* Create a markdown file in [`/docs/_course-notes`](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/docs/_course-notes)
* Follow the existing naming format used by other files in that folder
* Give your post some descriptive 'frontmatter', like this:

```
---
layout: page
title:  "Week 3: Laser cutter: computer-controlled cutting (CNC)"
date:   2018-11-23
author: Andrew Sleigh
---
```

### Adding images

Store all publishing assets in `/docs/assets`.

Include them on your page like this:

```
![programming boards diagram-sm.png]({{ "/assets/programming boards diagram-sm.png" | relative_url }})
```

Non-image assets should be stored in separate folders, e.g. `/docs/assets/file` or `/docs/assets/video`

### Adding links to other pages

Links to external pages use the standard markdown syntax (`[link text](http://example.com)`). To link to a page in this site (and for it to render properly on the [live website](https://fablabbrighton.github.io/digital-fabrication-module/), use this syntax:

```
[board programming guide]({{ site.baseurl }}/guides/guide-board-programming)
[DIY Arduino notes]({{ site.baseurl }}diy-arduino)
```


### Adding links to source code and other content in the github repo

Hopefully you are keeping things like [arduino code](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/arduino-code), [board designs](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/board-designs) and [3D files](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/3d-models) in this repo!

If so, you can link to them easily just like any other external URL ('external' because they are outside of the `/docs` folder). e.g. 

```
[Files on Github: `/board-designs/diy-arduino-0.1`](https://github.com/fablabbrighton/digital-fabrication-module/tree/master/board-designs/diy-arduino-0.1)
```


### Further help

Markdown: https://guides.github.com/features/mastering-markdown/
Jekyll and liquid syntax: https://jekyllrb.com/docs/




---

## Source material

Source material is credited on the appropriate pages. The course itself is largely derived from the content taught in [Fab Academy](http://fabacademy.org)
