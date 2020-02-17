---
title: "OpenSource Blogging with Jekyll GitHub VSCode Part1"
excerpt: "Kicking off the new year brought forward a renewed motiviation to join the community of tech bloggers. In this blog series I'll share everything you need to know to get you setup with your own blog site, for free, using open source tooling such as Jekyll, GitHub, and Visual Studio Code."
header:
  image: "/assets/images/Keep-Going.jpg"
  caption: ""
date:   "2020-02-17"
categories: 
- "BLOGGING"
tags: 
- "OPEN SOURCE"
- "GITHUB PAGES"
- "GITHUB"
- "GIT"
- "JEKYLL"
- "VSCODE"
- "MARKDOWN"
---
Kicking off the new year brought forward a renewed motivation to join the community of tech bloggers. In this blog series I'll share everything you need to know to get you setup with your own blog site, for free, using open source tooling such as Jekyll, GitHub, and Visual Studio Code.

* Part 1 - Why I'm using open source and an overview of my blog setup - `you are here`
* Part 2 - Getting started with a step-by-step guide
* Part 3 - Tips & tricks with Jekyll and Markdown editing
* Part 4 - Securing your content


To start off here's an overview of my blogging toolkit:

![OpenSourceBlogDependencies](/assets/images/OpenSourceBlogDependencies.png) 
> A collection of helpful links can be found [here][BloggingToolkit].

## Why OS?
Firstly let's talk about why I'm using open source, some of which may be relevant to your own goals and requirements.

### Zero Traffic, Zero Cost
When creating a new blog site with almost nil content and `zero traffic` my instinct was to keep costs minimal. For a new site that generates zero income I cannot justify spending even $1.00 per month on hosting costs or software licensing. Currently my blog is `zero cost` to my hip pocket which makes me happy :)

### Maximum Control, Minimal Effort
Being in a technical role I tend to deep-dive into solutions and explore the possibilities, things may break but I'll learn the what and why in the process. For this to happen I needed `maximum control` over content and delivery which led me to consider static websites as a good fit. Because static websites are the most basic type of website it's also perfect for new tech bloggers which means overall `minimal effort` to maintain long term.

### Familiar Tooling
As part of my 9-5 job I'm already using open source tools such as [Visual Studio Code][VisualStudioCode] to write/test my .ps1 and .azcli scripts and [GitHub][GitHub] to store/share my code in the cloud and apply version control. So it made sense to continue using `familiar tooling` and this greatly helped to reduce the time needed to deploy and maintain my blog. 

## Overview of Blog Setup
![OpenSourceBlogOverview](/assets/images/OpenSourceBlogDiagram.png)

### Local Dependencies
On my laptop I have the following clients installed:
- [Ruby][RubyInstaller] - `2.6.5`
- [Jekyll][JekyllWindowsInstall] - `4.0.0`
- [Visual Studio Code][VisualStudioCode] - `1.42.0`
- [Git][Git] - `2.18.0`

### Creating content
I create and modify content using the Visual Studio Code client. It has native support for markdown editing and integration with [Git][Git]. Maximum appreciation goes to VSCode's preview window which allows you to see the blog post as if it was live in a web browser.

> Note: You can also use GitHub from a web browser to create content via their GUI however you cannot preview the entire site without publishing it. This is the main reason I use my Surface Book 2 as a local dev environment.

### Previewing the Site
If I want to preview the entire site locally on my laptop I use:
```
bundle exec jekyll serve
```
This auto-builds & publishes the site at [http://127.0.0.1:4000][LocalSite]

### Online Publishing
My GitHub account has a single Repository and Master branch for the blog.

> Note: In order for GitHub Pages to automatically build and serve your blog content your GitHub Repository name needs be a certain format: `username.github.io`

When I'm happy with the local preview of the blog site I use Git from the VSCode Terminal to commit my local changes and push them to my GitHub Repo in the cloud. 

Your typical flow of commands will look like this:
```
git pull
git commit -am "commit message"
git push
```

The cool thing is GitHub Pages automatically detects changes to GitHub Repo's Master branch and using Jekyll integration auto-builds the site and publishes it live to [https://jesseloudon.github.io][JesseLoudonSite]

## Recap
In this blog I've provided you with a toolkit to get you started with open source blogging and summarised my reasons for going down this path. 

I've also given you a birds eye view of the blog setup and end-to-end flow of events starting from content creation to the blog post going live online.

In the next post I'll walkthrough how you can get started with your own blog on [GitHub Pages][GitHubPages] step-by-step.

[LocalSite]:http://127.0.0.1:4000
[RubyInstaller]:https://rubyinstaller.org/downloads/
[JekyllWindowsInstall]:https://jekyllrb.com/docs/installation/windows/
[JesseLoudonSite]:https://jesseloudon.github.io
[Part1]:"https://jesseloudon.github.io/blogging/OpenSource-Blogging-with-Jekyll-GitHub-VSCode-Part1/
[GitHubPages]:https://pages.github.com/
[GitHub]:https://github.com/
[Git]:https://git-scm.com/downloads
[VisualStudioCode]:https://code.visualstudio.com/download
[BloggingToolkit]:https://jesseloudon.github.io/BloggingToolkit/