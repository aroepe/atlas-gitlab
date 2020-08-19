---
title: "Creating a local repositry"
teaching: 10
exercises: 10
objectives:
- "Remind you how to create a _very basic_ repository"
- "Add your credentials to CERN's GitLab"
- "Push your simple `README.md`"
questions:
- "How do I create a simple repository?"
keypoints:
- "_Always_ add a `README.md` file to your repository"
- "Write verbose and useful commit messages."


hidden: false
---

In this episode we hope to demonstrate that "publishing" anything via
CERN GitLab is extremely easy.

## Create a base directory

We'll be working with this repository for the remainder of this
workshop, so before doing anything let's make sure you're putting your
code somewhere where you won't lose it! For instance, if you drop your laptop down the
hill [and one of the turkeys steals it!](https://www.youtube.com/watch?v=gR1nfWA-sEQ&feature=youtu.be)

> ## Code in Docker Containers/Images
>
> Be _very_ careful where you put your code while developing within
> containers! Nothing in the image is saved when you exit, so make sure you
> develop within the directories you've mounted on your laptop.
> **If you don't, then ask your instructor.**
>
{: .callout}

Start by creating a subdirectory like `bootcamp`. Personally
I keep my ATLAS projects under a directory called `~/work` but you can
adjust this as you see fit.

~~~
mkdir -p ~/work/bootcamp
cd ~/work/bootcamp
~~~
{: .source}

We'll do our work from here. That means we'll need:
- The pre-workshop material
- The input data file in a path like
  ~~~
  data/DAOD_EXOT27.17882744._000026.pool.root.1
  ~~~
  - If you don't have this data file, there are instructions to download it a later section

<!-- If you don't have this file locally, you need to download it:

~~~
mkdir data
cd data
wget https://cernbox.cern.ch/index.php/s/YXbCrQkwnZuc3yU/download
mv download DAOD_EXOT27.17882744._000026.pool.root.1
cd ..
~~~
{: .source} -->


> ## If you didn't do your homework
>
> You _really_ should set up the pre-workshop material.
> But we can continue by cloning it now and removing the `.git` directory.
>
> ~~~
> git clone ssh://git@gitlab.cern.ch:7999/usatlas-computing-bootcamp/v1-prework-finished-code.git pre-workshop
rm -rf pre-workshop/.git/
> ~~~
> {: .source}
>
{: .callout}


You can check your working directory with `tree .`. I get something like

~~~
.
├── data
│   └── DAOD_EXOT27.17882744._000026.pool.root.1
└── pre-workshop
    ├── AnalysisPayload.cxx
    ├── CMakeLists.txt
    └── README.md
~~~
{: .output}

## Initializing the repository

Now let's create a git repository. We create this in a _subdirectory_
of the working directory, because not everything we're working on will
be versioned.  GitLab only saves the stuff that we put in
this subdirectory.

~~~
mkdir amber-example
cd amber-example
git init
~~~
{: .source}

Where you should replace `amber` with your name. You should see
something like

~~~
Initialized empty Git repository in ...
~~~
{: .output}

where `...` is your working directory. If you try to commit something
now git will complain that there is nothing to commit. Git has good
intentions here: in general commiting nothing at all is a mistake.

> ## Name your repository carefully
>
> In general you shouldn't make a repository called `amber-example`. We've
> chosen this name to make it clear that this should be _your_ example with
> _your_ unique name. Our reason for this is pedagogical: we want everyone
> to develop their own code, but we also want you to be able to fork your
> friend's code and develop that. This would get very confusing if everyone
> used the same name.
>
> In a real world setting it would be very silly for everyone to name
> their code after themselves and rewrite it from scratch. Your repository
> name should reflect _what it does_ not _who wrote it_.
>
{: .callout}

## Adding a file

So let's add a file. Use your favorite text editor to create a file
called `README.md`. What you put here is up to you but _it will be the
first thing everyone sees when they look for your code_ so make it
count!

For now we'll describe what you're doing here. Add something like this

~~~
ATLAS Software Bootcamp
-----------------------

This is the README file for our bootcamp project.

Let's add some sugar and spice with Cupcake Ipsum!

Cupcake ipsum dolor sit amet gummi bears chocolate bar bear claw cake. Carrot cake pie donut croissant lollipop I love jujubes. Marshmallow I love muffin. Donut lollipop candy canes dragée wafer liquorice chocolate.

~~~
{: .language-markdown}

and save the file. (ipsum text generated at [Cupcake Ipsum](https://www.cupcakeipsum.com)) Let's ask git what is sees now:

~~~
git status
~~~
{: .source}

~~~
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)

	README.md

nothing added to commit but untracked files present (use "git add" to track)
~~~
{: .output}

Great, git sees the file but it's just floating around for now, we're not properly keeping it under version control. OK, let's add it to the index:

~~~
git add README.md
~~~
{: .source}

and check that it's been properly added

~~~
git status
~~~
{: .source}

~~~
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   README.md
~~~
{: .output}

> ## Turning Red to Green
>
> Git can color its text to make it easier on your brain. If you don't
> see untracked files in red and the `new file` as green, you can run
> ~~~
> git config --global color.ui auto
> ~~~
> {: .source}
{: .callout}

> ## Setting your name and email
>
> In the Git session you had to configure git to add your name and
> email to every commit, using `git config`. We'd recommend you use your
> CERN account email and name so that the names on local commits match the
> ones you'll create via GitLab.
>
> To change this you can run
> ~~~
> git config --global user.name <your cern name>
> git config --global user.email <your cern email>
> ~~~
{: .callout}


Great, now our `README.md` is ready to commit.

~~~
git commit -m "Add README file" -m "And a pretty poor README at that"
~~~
{: .source}

In general git will force you to create a commit message. You should
[try to write _good_ commit messages][good],
since this helps everyone understand what you were doing. In this case
it's pretty self-explanitory, but in many real-world examples a commit
might just change one line deep inside your code. A commit message is
a very good way to explain _why_ you decided to make this change.

Also note that a good commit message might run for several paragraphs
to explain the full context of the commit.
Each time you call `-m` it will start a new paragraph, which is convient
if you want to write a short (less than 50 characters is recommended)
description followed by a longer one.
If you need something more verbose, you can use the contents of a text
file with `git commit -F file.txt`.

This all might be review, but next the real fun begins: we'll push
this repository to GitLab.

[good]: https://chris.beams.io/posts/git-commit/
