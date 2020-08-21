---
layout: lesson
title: Introduction
root: .  # Is the only page that doesn't follow the pattern /:path/index.html
permalink: index.html  # Is the only page that doesn't follow the pattern /:path/index.html
---

{% include gh_variables.html %}

> ## Prerequisites
>
> This assumes that you'll have some basic background with git, for example:
>
> 1. How to get a local repository, in two ways
>     * using `git init`
>     * by cloning from GitHub
>
> 2. How to `branch`, `add` changes, `commit` them, and `push`
> 3. The basics of creating a merge request
>
> You should also have fully worked through the [pre-workshop material](https://adjackp.github.io/pre-workshopMaterial/). Having
> failed to complete this will make it very challenging and you will eventually have to go back and do this.  So take a few hours to
> be sure you have fully worked through that now.
>
{: .prereq}

Link Back to Bootcamp Material
___________

<div class="text-center">
<a href="https://urldefense.proofpoint.com/v2/url?u=https-3A__matthewfeickert.github.io_usatlas-2Dcomputing-2Dbootcamp-2D2020_&d=DwMFaQ&c=qKdtBuuu6dQK9MsRUVJ2DPXW6oayO8fu4TfEHS8sGNk&r=iUCOIf4F-Shz0fLCXgNmlaine-81S-jJCbZ4mzUe8Js&m=zP127KODA9oMd8yrk-U0Sw0CReuMURhyrrZZLJe0TRQ&s=nAtzZHy37PgYcSPEBjRdwjC4tU1XpYw61uIyig8DIXs&e=">
    <button type="button" class="btn btn-info" style="text-align:center">US-ATLAS Computing Bootcamp 2020</button>
</a>
</div>

Introduction
------------

In ATLAS we use use [GitLab](https://about.gitlab.com/)---basically an open-source replica of GitHub---to host our code.
Superficially the two have some confusing differences:

- The website layouts won't match and you may need to click differently to get the same buttons.
- GitHub is .com and owned/hosted by Microsoft, whereas ATLAS's GitLab is a cern-hosted instance of an open-source project ([https://gitlab.cern.ch/](https://gitlab.cern.ch/))
- GitHub encourages "pull requests" while in GitLab you must make "merge requests"

Fortunately, beyond this veneer the core concepts are nearly identical so everything you learned from the [Software Carpentry lesson](http://swcarpentry.github.io/git-novice/) applies.
The aim of this module is to expand on some concepts you learned in the morning and highlight a few of what we consider to
be essential skills to anyone working in ATLAS.

> ## The skills we'll focus on:
>
> 1.  The basic setup for CERN GitLab
> 2.  Creating a new repository for your AnalysisPayload from the [pre-workshop material](https://adjackp.github.io/pre-workshopMaterial/)
> 3.  Adding credentials
> 4.  Forking an existing repository so you can use it "like its your own"
> 5.  Creating merge requests to modify code in a way to ensure that it gets reviewed
> 6.  Including code from other repositories with yours through the use of submodules
{: .checklist}

{% include links.md %}

