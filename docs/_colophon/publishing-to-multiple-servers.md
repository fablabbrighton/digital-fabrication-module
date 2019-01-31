---
layout: page
title:  "Publishing to multiple servers"
date:   2018-11-24
author: Andrew Sleigh
---

Publishing this content to GitHub, GitHub Pages and my own server.
<!--more-->

I use quite a complex system to draft and publish these notes. This is an adaptation of [a system I first used for my Fab Academy documentation, detailed here](http://fab.academany.org/2018/labs/fablabbrighton/students/andrew-sleigh/assignments/2018/01/18/wk2-git-and-website.html). While fiddly to set up, it means I can write notes and share them with minimum friction, and maximum portability.

## My requirements

* Quickly take notes on WIP and write rough drafts without having to worry about publishing
* Use basic formatting and images without resorting to a complex word-processor (ie. Markdown)
* Selectively publish/share some of this content
* Easily create a navigable flat HTML website that I can publish to my own domain
* Share some WIP with collaborators on GitHub
* Publish navigable HTML version on GitHub Pages
* Combine drafting and publishing workflows with as few extra steps as possible

This is a more complex set of requirements than I used for Fab Academy, where I also used Jekyll to support a Markdown to flat-HTML drafting and publishing workflow. In that case, I was publishing HTML only (not Markdown), and only to one site. The publishing workflow there was simply a case of building the site to my local Git repository, then pushing that to the remote repo. The only complexity was that the URLs for my development server (localhost) and the live server were different. I handled this by using variables in the `_config.yml` file, and generating the files for local testing with an override for these live server URLs.

## Drafting
I’m currently using Bear (a Mac/iOS Markdown editor) for drafting notes) because it has great Markdown support and elegantly hides all the complexity. It has a pretty good Markdown export, the only problem being it hard-codes image links in a way that won’t work for my live sites. I may just switch to writing Markdown directly in a publishable format, using BBEdit (a text-only editor).

Drafting in an app like this introduces a break in the process, which has the downside of introducing a divergence as soon as I export a note to a Markdown file. From this point on, I have to treat the Markdown file in my Jekyll directory as the canonical note.

## Exporting Markdown
When an idea is solid enough to become a piece of content, I export the Bear note to a Markdown file in my Git repo. 

## Jekyll configuration
I set up the Jekyll `_config.yml` file to support publishing to GitHub Pages. I can’t control the Markdown-to-HTML conversion in this process, so it just needs to work by default. So I set up the URL variables like so:

```
url: “https://andrewsleigh.github.io” # the base hostname & protocol for your site
baseurl: “/digital-fabrication-module” # the subpath of your site
```

Jekyll can support multiple config files, so I created a second one, detailed below, to override these settings when publishing to my own site.

## Jekyll build and serve variants
Make sure we’re in the right directory first!
`cd /Users/Andrew/Documents/GitHub/digital-fabrication-module`

Update: I decided to move the non-code content to a /docs folder, so I'm now serving Jekyll locally from `/Users/andrew/Documents/GitHub/digital-fabrication-module/docs`

Then, depending on what I’m trying to do, I can use different versions of the Jekyll command to generate the site:

### Pushing to the remote repo on GitHub and publishing to GitHub Pages
No Jekyll build needed as I’m pushing Markdown files to GitHub, not HTML!

### Serving the site for local testing
`bundle exec jekyll serve --baseurl ''`
This generates the static HTML files indie a `_site/` directory, which is then served from <http://127.0.0.1:4000>
This also auto-regenerates the site with every change.

### Building the site for deploying to my live server
`jekyll build --destination _site-ascom/ --config _config.yml,_config-ascom.yml`

This builds the site (without auto-regeneration) to a folder, `_site-ascom/` and it uses the `--config` option to read from two configuration files. The first is the main `_config.yml` file which has all the basic options set for the site, including `url` and `baseurl` as mentioned above.

The second has only two lines, and overrides these settings with ones appropriate for hosting on my site:
```
url: "https://andrewsleigh.com"   
baseurl: "/learning/digital-fabrication-module"
```

## Filepaths
In general, Jekyll is set up to use relative file paths, and these work fine, so long as the site is built or served using the appropriate options as above.

## Image paths
This is how I include an image in a Markdown file. (`assets/` is a directory at the root level of my Jekyll site.)

```
![laser-printer-driver-dialog.jpg]({{ "/assets/laser-printer-driver-dialog.jpg" | relative_url }})
```

On GitHub Pages, this renders as:
`<img src="/digital-fabrication-module/assets/laser-printer-driver-dialog.jpg" alt="laser-printer-driver-dialog.jpg" />`

On my localhost, when serving with `baseurl ‘’`, it renders as:
`<img src=“/assets/laser-printer-driver-dialog.jpg” alt=“laser-printer-driver-dialog.jpg” />`

On my live site, when building with `--config _config.yml,_config-ascom.yml`:
`<img src="/learning/digital-fabrication-module/assets/laser-printer-driver-dialog.jpg" alt="laser-printer-driver-dialog.jpg" />`

## Publishing and version control
This Jekyll directory is a Git repo on my own development machine. Jekyll can build the site and serve it locally from  <http://127.0.0.1:4000>. I can also publish it to my three public destinations:

### 1. GitHub
<https://github.com/andrewsleigh/digital-fabrication-module>
This is the home for Markdown files and other assets I would like others to contribute to or adapt themselves.
I can just push changes to the GitHub repo to share them publicly. 

#### A note on Gitignore

The local repo has two folders of static HTML files that don’t need to be synced with GitHub (or indeed controlled with Git locally). So I created a `.gitignore` file at the root of this repo to exclude these two folders from Git:

```
/_site/
/_site-ascom/
```

Actually removing them from the Git repo is a bit more fiddly, since they had already been included in previous commits. [StackOverflow to the rescue](https://stackoverflow.com/questions/7927230/remove-directory-from-remote-repository-after-adding-them-to-gitignore):

> The rules in your .gitignore file only apply to untracked files. Since the files under that directory were already committed in your repository, you have to unstage them, create a commit, and push that to GitHub:  
> ```  
> git rm -r --cached some-directory  
> git commit -m ‘Remove the now ignored directory “some-directory”’  
> git push origin master  
> ```  

In my case:
```
git rm -r --cached _site-ascom
git commit -m 'Remove the now ignored directory "_site-ascom"'
git push origin master

git rm -r --cached _site
git commit -m 'Remove the now ignored directory "_site"'
git push origin master
```

This worked, so I added a few more entries to hide some other superfluous files from the public repo:

```
/Gemfile        // Update: See warning below
/Gemfile.lock
**/.DS_Store
/.sass-cache
```

`**/.DS_Store` should match macOS’s `.DS_Store` files whichever directory they’re in.

And then I followed the same procedure to remove these already-committed files from the repo.

**Update:** of course you can't remove the `Gemfile` and perhaps not `Gemfile.lock` or `.sass-cache`, or Jekyll won't run locally, so I ended up putting these back in the repo, and removing these lines from .`gitignore` 


### 2. GitHub Pages

<https://andrewsleigh.github.io/digital-fabrication-module>

I use the [built-in GitHub Pages tool](https://pages.github.com) to publish these Markdown files to a normal HTML website, also using Jekyll. You can do this without setting your repo as a Jekyll instance, but as I want to create an HTML site myself anyway, [this is a lot easier](https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages/), and I can control the design of the site using the same config settings and templates.

‘Publishing’ is automatic once setup, and changes are regenerated on the live GitHub Pages site after every push to the GitHub repo.

### 3. My own site

<https://andrewsleigh.com/learning/digital-fabrication-module/>

I want to maintain a copy of the site at a  URL I control. I don’t have any syncing tools set up with my web host, so periodically, I just use SFTP to sync the `/_site-ascom` directory with the `/learning/digital-fabrication-module/` directory on my site.

