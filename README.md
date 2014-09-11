# Be kind to the people you work with

So, you are all comfy at your couch, the beer is cold, you are starving but you are waiting for the film to start before having a go at the pizza. You turn on the [vcr](http://en.wikipedia.org/wiki/Videocassette_recorder), put the [tape](http://en.wikipedia.org/wiki/VHS) in and press play, only to find out that the tape has reached the end. Wouldn't it be awesome if the person that watched it before you had rewinded? Wouldn't it be awesome if the person that picks the last tissue replaces the toilet paper? Imagine if we all pressed the toothpaste only from the end up.

It is these simple things in life that make everybody happy. You can make the people you work with happy by tidying up after yourself and git lets you do this really easy. What follows is some very simple techniques to make sure you achieve an awesome git workflow.

![alt text](git-r-done.gif)

## Table of Contents

* [An introduction](#an-introduction)
  * setup, global variables, colors, editor, github config, ssh values (linux), prefer ssh cloning
* [Branching out](#branching-out)
  * references, hashes, HEAD, ~/^ difference
* [Commit messages](#commit-messages)
  * title, description (bullet points, code explanation if needed), 80 char limit, # in editor, no '.' in title
* [Commit often, push once](#commit-often-push-once)
  * try to squash commits for whole feature, or many commits under the same concept
* [Avoiding merge commits](#avoiding-merge-commits)
  * pull --rebase, when can you use it?
* [Rebasing](#rebasing)
  * published changes, explanatory diagram
* [Cherry picking](#cherry-picking)
  * also for ranges
* [Tagging](#tagging)
* [Stashing](#stashing)
* [Bisect](#bisect)
* [Frequently used commands](#frequently-used-commands)
  * git branch -r, log .., show
* [Shortcuts](#shortcuts)
  * aliases
* [GitFlow](#gitflow)
* [Resources](#resources)

## An introduction

This isn't a proper introduction. This [book](http://git-scm.com/book) has one though, and I think that chapters 1-3 are required reading. Most of the things written here come from that books, or various articles in the wild.

Before you are ready to start working, it is essential that you have git well set up. There are two ways you can tell git about you and your preferences. 

The first is the `/etc/gitconfig` file. You can override settings in a separate `~/.gitconfig` file, which is the next place git will look for configuration. Lastly, git will look at project specific `.git/config` files which will in turn override all the rest.

You can also set configuration through the `git config` command. Use 

`$ git config -h` 

to see all the available options.

First of all, you should introduce yourself to everybody and start taking responsibility for your code. You do this with

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```
You are going to be writing a lot of comments explaining your changes so it's nice to use an editor you are comfortable with

```
$ git config --global core.editor emacs
```
This works with GUI editors too, like Sublime Text.

Since you will be looking at a terminal most of the time, it makes some sense to have git use colored output. You can look at the `color.*` configuration options. You'll most likely want to leave this setting to `auto`, so that git colors all output directed to the terminal.

```
$ git config --global color.ui auto
```

## Branching out
TODO

## Commit messages

Communicating your changes to the rest of the team is crucial. At any given time, you want every member to have an idea of what is going on to the project. The business rules for a new feature. A new css mixin you just pushed. Some addition to a library that might break somebody's changes. As much self explaining as your code may be it takes longer for someone to understand what's going on and track all changes individually than providing a simple description and explanation of the changes. It also speeds the reviewing process a lot. The reader can quickly grasp what's going on.

Structure your commit message like this:

```
Short (80 chars or less) summary of changes

More detailed explanatory text, if necessary.  Wrap it to about 80
characters or so.  In some contexts, the first line is treated as the
subject of an email and the rest of the text as the body.  The blank
line separating the summary from the body is critical (unless you omit
the body entirely); tools like rebase can get confused if you run the
two together.

Further paragraphs come after blank lines.

 - Bullet points are okay, too

 - Typically a hyphen or asterisk is used for the bullet, preceded by a
   single space, with blank lines in between, but conventions vary here
```

Do not assume that the reader understands the original problem or knows the context, even if it is obvious. New members come to the team and what makes sense today can be easily forgotten in the future. Reference the issue in the commit title (TODO). It helps when you want to find all the code changes related to a specific feature.

Refrain from trying to reproduce the feature description or specs in the commit message. Just try to describe your changes and the rationale behind them in simple English. Take your time when commiting, read your message out loud so that you know it makes sense.

## Commit often, push once
TODO
