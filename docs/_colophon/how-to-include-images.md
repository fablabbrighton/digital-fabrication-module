---
layout: page
title:  "How to include images on a page on this site"
date:   2019-02-21
author: Andrew Sleigh
---
How do you embed an image on a github.io website?

<!--more-->


## Jekyll Liquid syntax

Jekyll (which Github uses to render Markdown files to HTML) uses a templating system called <a href = "https://jekyllrb.com/docs/liquid/filters/">Liquid</a> to allow for dynamic content to be inserted.

This means that you can use a short image embed code that will work on any site, including a localhost testing server. Assuming you're putting your images in the `docs/assets/` folder, this code put an image on the page on it's own line:

```
![Image test]({{ site.baseurl }}/assets/stem-dimensions.jpg)
```

This renders (when served on github.io) as:

```
<p>
  <img src="/digital-fabrication-module/assets/stem-dimensions.jpg" alt="test">
</p>
```

## Github image URLs

Note that a URL like `https://github.com/fablabbrighton/digital-fabrication-module/blob/master/docs/assets/stem-dimensions.jpg` doesn't point to an image, but to a webpage on GitHub.

