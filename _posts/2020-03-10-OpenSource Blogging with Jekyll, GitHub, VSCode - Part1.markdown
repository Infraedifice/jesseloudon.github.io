---
title:  "OpenSource Blogging with Jekyll, GitHub, VSCode - Part1"
excerpt: "Kicking off the new year brought forward a renewed motiviation to join the community of tech bloggers. In this blog series I'll share everything you need to know to get you setup with your own blog site, for free, using open source tooling such as Jekyll, GitHub, and Visual Studio Code."
header:
  image: "/assets/images/Keep-Going.jpg"
  caption: ""
date:   "2020-02-12"
categories: 
- "BLOGGING"
tags: 
- "OPEN SOURCE"
- "GITHUB PAGES"
- "GITHUB"
- "JEKYLL"
- "VSCODE"
---
Kicking off the new year brought forward a renewed motiviation to join the community of tech bloggers. In this blog series I'll share everything you need to know to get you setup with your own blog site, for free, using open source tooling such as Jekyll, GitHub, and Visual Studio Code.

* [Part 1 - Why I'm using open source and an overview of my blog setup][Part1]
* Part 2 - Getting started - a step-by-step guide
* Part 3 - Tips & tricks with Jekyll and Markdown editing
* Part 4 - Securing your content

To start off here's an overview of my blogging toolkit:
![OpenSourceBlogDependencies](/assets/images/OpenSourceBlogDependencies.png) 
> A collection of helpful links can be found [here][BloggingToolkit].

## Why OS?
Firstly let's talk about why I'm using open source, some of which may be relevant to your own goals and requirements.

### Zero Traffic, Zero Cost
When creating a new blog site with almost nil content and `zero traffic` my instict was to keep my costs minimal. For a new site that generates no income I simply cannot justify spending even $1.00 per month on hosting costs or software licensing. Currently my blog is `zero cost` to my hip pocket which makes me happy.

### Maximum Control, Minimal Effort
Being in a technical role I tend to deep-dive into solutions and explore the possibilities, things may break but I'll learn the what and why in the process. For this to happen I needed `maximum control` over content and delivery which led me to consider static websites as a good fit. Because static websites are the most basic type of website it's also perfect for new tech bloggers which means overall `minimal effort` to maintain long term.

### Familiar Tooling
As part of my 9-5 job I'm already using open source tools such as [Visual Studio Code][VisualStudioCode] to write/test my .ps1 and .azcli scripts and [GitHub][GitHub] to store/share my code in the cloud and apply version control. So it made sense to continue using `familiar tooling` and this greatly helped to reduce the time needed to deploy and maintain my blog. Maximum appreciation goes to VSCode's built-in support for markdown editing and the preview window (more on this later).


![OpenSourceBlogOverview](/assets/images/OpenSourceBlogDiagram.png)
My Surface Book 2 is my local development environment where I create content and view my local blog at http://127.0.0.1:4000 before pushing commited changes to my GitHub Repository.

I have the following clients installed:
- Ruby - 2.6.5
- Jekyll - 4.0.0
- Visual Studio Code - 1.42.0
- Git - 2.18.0

My GitHub account has a single Repository and Master branch for the blog. In order for GitHub Pages to automatically build and serve the blog content my GitHub Repository name needs be a certain format:

`username.github.io`


[Part1]:"https://jesseloudon.github.io/OpenSource-Blogging-with-Jekyll,-GitHub,-VSCode-Part1/"
[Jekyll]:https://jekyllrb.com/
[JekyllWindowsInstall]:https://jekyllrb.com/docs/installation/windows/
[GitHubPages]:https://pages.github.com/
[GitHub]:https://github.com/
[GitHubGuides]:https://guides.github.com/
[RubyInstaller]:https://github.com/oneclick/rubyinstaller2/releases
[MinimalMistakes]:https://mmistakes.github.io/minimal-mistakes/
[MinimalMistakesQuickStart]:https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/
[GitHubHostedRunnersAzure]:https://help.github.com/en/actions/reference/virtual-environments-for-github-hosted-runners
[VisualStudioCode]:https://code.visualstudio.com/download
[BloggingToolkit]:https://jesseloudon.github.io/bloggingtoolkit