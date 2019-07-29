---
layout: post
title: Virtual Environments in Python (And More)
date: 2019-02-05T02:01:00.000Z
description: Virtual environments are something that changed my development preferences on using them when I began more serious development in Python around 5 years ago. However, admittedly at first they can be challenging. That’s why I’ve decided to write a really brief introduction on the benefits, uses and drawbacks of virtual environments in python. I’ll also cover some other interesting virtual environment possibilities, and upcoming news.
categories: 
tags:
  - python
excerpt_separator: <!--more-->
---
Virtual environments are something that changed my development preferences on using them when I began more serious development in Python around 5 years ago. However, admittedly at first they can be challenging. That's why I've decided to write a really brief introduction on the benefits, uses and drawbacks of virtual environments in python. I'll also cover some other interesting virtual environment possibilities, and upcoming news. 

<!--more-->

🏊 Let's dive in!

When I first began with virtual environments, I was thrown into a code base with multiple environments, on multiple servers, with little instruction. But that trial by fire helped solidify what virtual environments were to me (through many errors and mistakes), and I still use them (by choice) to this day. Albeit, if you can avoid learning about them that way, I would recommend it 😂.

The technical definition of virtual environments is that they are “a self-contained directory tree that contains a Python installation for a particular version of Python, plus a number of additional packages.”

In plain English they are isolated installations of Python, that allow you to install certain packages and programs without affecting other projects, or your system installation of Python. This has the advantage of making it easy to change projects, install different versions of programs, and just generally be somewhat care free when choosing packages, without worrying if your changes will affect other programs on your machine or server.

# Why Use Virtual Environments?

There are four major reasons to use virtual environments. And even if your not sure whether or not to use them, it's still a good idea, so that you don't mess up your system level python installation.

* **Isolate your program or app from your System's packages:** Like we discussed, don't worry about breaking python globally, and just worry about your app.
* **You may need to run a custom version of a Python package, or Python:** If your program requires an old package that might break other programs, this allows you to install it without worrying. You can even use a different version of Python all together.
* **Your app may have unique package requirements:** Similar to separate versions, if your app requires a modified or unique package, or fine grained control, virtual environments let you do that on a per app basis.
* **You may have multiple programs, all with different requirements:** With virtual environments, whether you have 1 or 100 apps on your machine, you don't have to worry about your Python system installation causing them to break.

# Why Virtual Environments can Suck

* **They can be complex:** Setting up a new environment on a per project basis, it can be difficult to remember project requirements, activation/deactivation, and installation locations.
* **There is a somewhat steep learning curve:** I know from experience that the concept is not entirely friendly to new developers. But it is simple when properly explained.
* **Environments live in isolation:** These environments don't persist beyond terminal sessions, and need to be activated in order to use.

# How to Use Virtual Environments in Python?

Very briefly, I'll go over the four commands needed to use virtual environments in Python. We'll cover creation, activation, deactivation, and removal.

First you'll need to [install virtualenv](https://virtualenv.pypa.io/en/stable/installation/) (or another variant depending on your OS). If you're an Ubuntu user this can be [somewhat complicated](https://askubuntu.com/questions/603935/pyvenv-vs-venv-vs-python-virtualenv-vs-virtualenv-and-python-3)...

After you have virtualenv installed things get pretty simple. I'm just going over the [commands covered in the virtualenv user guide](https://virtualenv.pypa.io/en/stable/userguide/).

Create your Python virtual environment:

```
$ virtualenv env
```

Activate your Python virtual environment:

```
$ source /path/to/env/bin/activate
```

When your environment is activated, you will see the name of your environment in parenthesis before your terminal prompt, like this:

```
(env) $
```

Deactivate your Python virtual environment:

```
$ deactivate
```

Remove your Python virtual environment:

```
(env) $ deactivate
```

```
$ rm -r /path/to/env
```

That's it! That's really all you need to know in order to get started using virtual environments. I recommend understanding what package to use on your OS, and the differences and nuances of each, but once you have it installed properly, created, and running, it should be smooth sailing from there!

# Can Other Languages Use Virtual Environments?

Yes!

JavaScript has it's own Node.js virtual environment called [nodeenv](https://github.com/ekalinin/nodeenv). This works great for development in JavaScript, and I've been using it for a variety of React and GatsbyJS projects. This very website was developed within a nodeenv environment.

# Upcoming News

All that being said there are some new developments on the horizon regarding virtual enviroments. Specifically PEP 582, a proposed Python local packages directory. [Detailed here](https://medium.com/@grassfedcode/goodbye-virtual-environments-b9f8115bc2b6). 

> PEP 582 "This PEP proposes to add to Python a mechanism to automatically recognize a \_\_pypackages\_\_directory and prefer importing packages installed in this location over user or global site-packages. This will avoid the steps to create, activate or deactivate “virtual environments”. Python will use the\_\_pypackages\_\_ from the base directory of the script when present."

This could be interesting, but I'll have to see how things play out before I significantly change how I use virtual environments in Python, or elsewhere.

<hr />

Because virtual environments can be quite complex. [Especially when it comes to installation.](https://askubuntu.com/questions/603935/pyvenv-vs-venv-vs-python-virtualenv-vs-virtualenv-and-python-3) There are still reasons to look for improvements. But by and large, virtual environments are one of my favorite things about Python development, and I've carried them over to JavaScript (Node) because of how useful they can be. I hope they are here to stay, and I hope they improve.
