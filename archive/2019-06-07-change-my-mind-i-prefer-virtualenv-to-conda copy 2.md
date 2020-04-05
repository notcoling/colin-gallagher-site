---
layout: post
title: 'Change my Mind: I Prefer Virtualenv to Conda'
date: 2019-06-07T15:42:51.664Z
description: Should I be using Conda? I've been seeing Conda appear more frequently online, and I recently tried re downloading and using Anaconda. I've tried to use Conda in the past. And after trying it again, I feel like I may be an outlier, but I just don't see the value over Python's traditional virtual environments (for medium sized projects). 
categories: 
tags:
  - python
excerpt_separator: <!--more-->
---
I've been seeing [Conda](https://docs.conda.io/en/latest/) appear more frequently online, and I recently tried re downloading and using [Anaconda](https://www.anaconda.com/). I've tried to use Conda in the past. And after trying it again, I feel like I may be an outlier, but I just don't see the value over Python's traditional virtual environments (for medium sized projects). 

<!--more-->

<iframe src="https://giphy.com/embed/xT1R9BLOlJKAbuc1MY" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/sharktank-shark-tank-918-xT1R9BLOlJKAbuc1MY"></a></p>

## Change My Mind

I'll explain in brief why I'm not sold on Conda. But I'd love for more information, and for someone to change my mind! Please reach out to me on Twitter [@notcolinn](https://twitter.com/notcolinn).

If you need a look into what virtual environments are, and why you might use them, [I wrote a post on that here](https://colingallagher.me/blog/2019-02-06-virtual-environments-in-python-and-more/).

## Conda

Conda is certainly more fully featured, and almost seems to work like magic. There is simple syntax to create environments, install different versions of Python, and install packages. However, [the installation process](https://docs.anaconda.com/anaconda/install/) (on both [Linux](https://docs.anaconda.com/anaconda/install/linux/) and [Windows](https://docs.anaconda.com/anaconda/install/windows/) (although admittedly I've not tried the Windows one)) seems needlessly complex.

After you have it installed, getting up and running in Conda For example works something like this (create a new environment 'myenv' and install the package 'biopython'): 

`$ conda create --name myenv biopython`

To activate your new enviroment:

`$ conda activate myenv`

You can also invoke more detail in your installation, like this (new environment named “myenv” using Python 3.4, 'scipy' version 0.15.0, and packages 'astroid' and 'babel' of any version). 

`$ conda create -n myenv python=3.4 scipy=0.15.0 astroid babel`

To deactivate Conda:

`$ source deactivate`

You can then remove an enviroment if you want to using this command:

`$ conda env remove -n ENV_NAME`

That's all fairly straight forward right?

## Virtualenv

[Virtualenv](https://virtualenv.pypa.io/en/latest/), my go to for virtual environments in Python, is slightly different. You need to have python installed on your system, and have 'virtualenv' installed through a package manager like Pip (ironically you can also use Conda, but thats something for another blog post).

Installing virtualenv is easy:

`$ pip install virtualenv`

After you have it installed, getting up and running is still pretty easy as well:

`$ virtualenv myenv`

Activate your new environment:

`$ source myenv/bin/activate`

However, you will need to then Install your packages separately once your environment is activated:

`$ pip install biopython`

You can invoke more detail in virtualenv as well (This command will install python3.4, however you need to first install Python 3.4 on your system):

`$ virtualenv --python=/usr/bin/python3.4 myenv`

You can then pip install more detailed packges like so (This command will install 'scipy' version 0.15.0):

`$ pip install scipy==0.15.0`

To deactivate a virtualenv enviroment is as easy as:

`$ deactivate`

Very similar to Conda, but again, with less of the process hidden away behind a single command.

## Python3

New to Python3 ([as of version 3.3](https://docs.python.org/3/library/venv.html)) is venv, which icludes this kind of behavior out of the box with Python3! I have been using this more extensively on new projects because it is just so easy.

There is no need to install venv as it comes part of Python3. Which is really cool, and fitting now that [Python 2 is near its EOL](https://pythonclock.org/). All the more reason to switch to Python3 if you have not already.

To create a new venv virtual environment, the command looks like this:

`$ python3 -m venv /path/to/new/virtual/environment`

The activation command is very similar (read identical) to Conda and Virtualenv:

`$ source <venv>/bin/activate`

Installing programs is done again, through Pip. Detailed new enviroments and installs will need to be carefully constructed again using Pip. And the [Venv documentation](https://docs.python.org/3/library/venv.html) does not clearly call out how to use other versions. Most likely you will need to separately install the Python3 version you would like to use on your system.

Deactivation is again the same as the others:

`$ deactivate`

This will probably become my go to choice, as it comes installed with Python3. So there's no extra work once you've installed Python on your system.

## Nodeenv

I also use a [Nodeenv](https://github.com/ekalinin/nodeenv), which is a Pip installed package that helps me manage NodeJS environments like I do Python. This may not be the best way, but it works for managing various websites and projects that I have in process at any given time.

The install is done through Pip, and the activation and setup are exactly the same as Virtualenv. Packages can then be downloaded through NPM like any normal NodeJS project. Deactivation and deletion work the same as well.

## So Why Use Conda?

Given the above workflows I just don't see how Conda is much better at helping me manage projects (keep in mind, most projects I'm working on are small to medium in complexity).

Virtualenv, Venv, and Nodeenv appear to have fewer moving parts, and are not that much work to install and have up and running on a system. It's also easy to move projects from one machine to another using them without much hassle. 

Not to mention if something goes wrong with them, I know how to debug the problem. 

Given the more complicated install and management of Conda, I'm not sure I could be as effective if something went wrong on a project related to the environment I was using.

And for those reasons, I"m out.

<iframe src="https://giphy.com/embed/xT1R9N29oJ3ZISU9oI" width="480" height="270" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/sharktank-shark-tank-sharktankabc-xT1R9N29oJ3ZISU9oI"></a></p>
