---
title: "GitLab Interface"
teaching: 10
exercises: 10
objectives:
- "See a sample of the features available in the GitLab web interface"
- "Give another user permissions on your repository"
questions:
- "What can I do on the GitLab website?"
keypoints:
- "The web interface is very powerful and provides many options for managing your code and your repository."
- "Through the web interface you can manage who is allowed to develop code."

hidden: false
---

## What is the GitLab interface?

Throughout this lesson you have been implicitly interacting with the GitLab interface.
Strictly speaking, a git server is just a central server that stores many other repositories.[^1]
This does not need web interface to operate. 
However, there are many features provided by GitLab (and GitHub, etc.) that allow 
management and automation of your code that are incredibly powerful.

You've already seen, for example, the merge request interface 
and how many tools are at your disposal to discuss and approve changes. 
(To see merge requests in action, take a look at the [MRs in progress](https://gitlab.cern.ch/atlas/athena/-/merge_requests) for the ATLAS Athena software)

In this episode we'll look at some of the most used tools and features that are used in day-to-day development.


[^1]: Note There are [many other configurations](https://git-scm.com/book/en/v2/Distributed-Git-Distributed-Workflows) 
        of git repositories. You will likely always be working with the _Centralized Workflow_ setup of having your code 
        on one or more development machines that all point to the same central server

## The repository sidebar

Almost everything you might want to do with your repository begins at the **sidebar**. 

<img src="{{ page.root }}/fig/sidebar.png" alt="Sidebar" width="15%" style="float:center" />

The tools you might want to use are separated into groups in the sidebar. You may have to browse through a few groups before you find what you're looking for.

Click on the repository name, in this case `amber-example` to come back to the home page of the repository. 

## Graph

A very useful tool for both simple and complex repositories is the **graph** display. This will show you a graphical representation of the commit history including who made the commit, the short commit message, branches, merges and other useful information. It is located under the *repository* group.

<img src="{{ page.root }}/fig/graph.png" alt="Sidebar" width="60%" style="float:center" />

> ## Exercise: look at the graph display of your repository
>
> <img src="{{ page.root }}/fig/graph.gif" alt="Sidebar" width="30%" style="float:center" />
>
> Now try clicking on a specific commit. What do you see? What page has it brought you to in the sidebar?
> 
{: .challenge}


## Members

One thing you may do with you analysis team is develop code together quite frequently. You may want to include other people as developers on your repository which will allow them to make branches without needing to fork the repository. Fortunately this is easy to do in the GitLab interface.

The **Members** page allows you to invite other users or groups to be developers. There are a few [permission levels](https://gitlab.cern.ch/help/user/permissions) you can choose for these new users.


> ## Exercise: add your new friend as a developer on your repository
>
> First, click the **Members** button in the sidebar. This will bring you to a page listing the current members
> and give you the option to add a new one.
>
> Add your friend to your repository as a developer. Type their name or CERN username in the first field,
> and select *Developer* from the dropdown in the second field.
>
> Finalize by clicking the green *Invite* button.
>
> <img src="{{ page.root }}/fig/add-member.png" alt="Sidebar" width="40%" style="float:center" />
> 
{: .challenge}


GitLab cleverly assumes you don't want those with developer or reporter roles 
to start messing with your stable master branch without going through the steps of a merge request. 
The master branch is given *protected* status.

You can see this by following **Settings > Repository > Protected Branches** (click the expand button to see the protected branches).

## Other useful interfaces (bonus section)

There are several other features of GitLab that could take whole lessons to fully explore. Listed below are a few that are good to be aware of.

### Issues
The GitLab issue tracker is a flexible tool for keeping track of bugs, requested features, user questions, or any other aspect of the code that needs addressing. Issue trackers are widely used in software development. [Here are some reasons why](https://sifterapp.com/academy/overview/why/), as well as a more in-depth description of what they can do.

I would recommend using the issue tracker for even small projects. 
- It is much easier to keep track of several development threads than in a Skype chat or email.
    - The thread is then part of the code's documentation if future developers (yourself included) want to take a look at how a decision was reached.
- You can directly reference commits and lines of code from the issue, and vice versa.
- You can easily include other developers and experts in the conversation.

> ## Bonus Exercise: create a new issue in your repository
> Click the **Issues** tab in the sidebar, and then the green **New issue** button.
> Maybe your issue could be *Implement continuous integration*. Or anything else you choose.
{: .challenge}


### Continuous Integration / Continuous Deployment (CI/CD)
One of the most useful tools in GitLab is its ability to automate code compilation, testing, and running.
There will be a full day of this tutorial series dedicated to just this aspect of GitLab, so little detail will be given here.
The main idea is, every time a change is made to the code, GitLab can trigger a series of scripts that ensure what just changed won't break the expected behavior.
This can be very valuable for repositories with one developer, or several hundred.

### Web IDE

Sometimes you want to make a small change to the code, documentation, or CI/CD scripts without opening a shell.
GitLab has a fairly nice *Web IDE* that lets you do this pretty seamlessly. (IDE is a pretty big claim for this pretty minimal text editor, but ok...)

Simply go to the file you want to edit in **Repository > Files** and click the **Web IDE** button 
(or the **Edit** button which will take you to a simpler editor). Edit your file, click **Commit**, and write your (descriptive) commit message. You can decide to commit to the current branch, make a new branch, and/or start a merge request.

**Don't forget to pull your code once you start editing in your normal development environment.**

> ## Bonus Exercise: edit `AnalysisPayload.cxx` in the browser
> Navigate to **Issues > Files > AnalysisPayload.cxx** and click the **Web IDE** button.
>
> Add some comments or new code and create a commit with a new branch.
{: .challenge}

### Everything Else!

There are many many other features GitLab has to offer. Take some time to explore the menus and click some buttons. There is [extensive documentation](https://gitlab.cern.ch/help), and if you have any questions, please feel free to ask an instructor!
