---
layout: post
title: Using Git with Alteryx
date: 2019-06-07T00:16:30.679Z
description: >-
  What is Version Control Anyways? I like certain aspects of software development. And I wish some things were
  more available when working on other kinds of projects. Thankfully, there are
  some things that carry over. Like version control.
categories: 
tags:
  - alteryx
  - git
excerpt_separator: <!--more-->
---
## What is Version Control Anyways?

Version control at a high level is just the process of tracking changes in projects and files. Each time something changes it gets assigned an ID and a timestamp which can be tracked. These 'Revisions' can be compared, restored, and with some types of files, merged.

<!--more-->

Git (probably the most popular version control software), according to Wikipedia, is a distributed version-control system for tracking changes in source code during software development. So basically, git is a version control tool made specifically to be good a versioning and managing code.

We'll be discussing version control and specifically Git throughout this article. So don't be shy and feel free to read up a bit if you have no idea what those are, or if you think I've done a terrible job summarizing them. These are some of my favorite resources for learning, and developing a deeper understand of version control, and Git. 

* [Github: Learn Git](https://try.github.io/)
* [Git: About Version Control](https://git-scm.com/book/en/v1/Getting-Started-About-Version-Control)
* [Codecademy: Learn Git](https://www.codecademy.com/learn/learn-git)
* [Getting Git Right from Atlassian](https://www.atlassian.com/git)

## Should It be used outside of Software Development?

Yes. Although admittedly, it can be a bit complex if you don't come from the world of software.

Version control, and utilizing git for saving and syncing files is something that hasn't really been replicated well outside of software development.

Sure there are cloud based document sharing services like Google Drive, Dropbox, and others. But when it comes to working on files with colleagues in other domains (like Data Science for instance) there is not a good solution for collaboration. Data Science has the advantage of being a software heavy domain where Git can still be used on most projects. But I'm thinking specifically for collaborating by working on a project, in a non-code based software application separately, and combining work.

By this I mean, we each are working on the same project, and have a copy of it open on our computers. And when we save our work we'd like to consolidate our changes.

When working on two separate things within the same file, the way to combine those things would be to just open both, and copy/paste from one into the other.

Seems easy enough, until you realize that many applications either won't allow the copy/paste, don't save state properly when doing so, or require additional configuration in order to behave properly.

Not to mention the fact that this requires sending and sharing independently anyways.

## Git Version Control with Alteryx files

An example of being able to do this in my work, is when I work with Alteryx files.

Alteryx is a quick-to-implement end-to-end data analytics platform that allows data scientists and analysts alike to analyze and organize data using drag and drop tools.  It helps you create workflows to combine, clean, analyze, and understand data.

Alteryx files, when saved are essentially stored as XML, which means that version control systems like Git won't have a hard time managing the files!

Here is a basic example of what managing a project in Alteryx looks like:

Create a project:

![Create Project]({{site.baseurl}}public/img/2-files.png)

Edit the project:

![Inside Project]({{site.baseurl}}public/img/1-create.png)

Initialize a Git repository inside your project directory:

`$ git init`

Add the files you want to track to your Git repository:

`$ git add .`

Create your first commit with your tracked files:

`$ git commit -m 'initial commit'`

You should get something like this after you enter the commit command:

![Git Commit Result]({{site.baseurl}}public/img/6-git-commit-result.png)

Setup a repository in your repository manager of choice (Github, Bitbucket, Gitlab), in this case I'll be using GitLab:

![GitLab Project]({{site.baseurl}}public/img/7-gitlab.png)

When you have your project set up in your repository manager, you'll need to add the link to the project as a 'remote' in your local Git project:

`$ git remote add origin https://github.com/your/project/url.git`

Push your project files to your repository manager:

`$ git push -u origin master`

Now you should be able to see your project files in your repository manager!

Your files are now being tracked via Git, and are available for others to download and use via your repository manager. Talk about practical and efficient. 

This same basic workflow can also be applied to other data science and visualization tools like Tableau! Which means that projects don't have to be shared just using shared folders and the occasional email. They can be placed somewhere useful and accessible for the entire team, like Gitlab.

## Using Git as a vehicle for Organization

Versioning is not the only advantage of using Git.

Another advantage is creating a repository of projects that can be accessed and viewed in an easy to access and organized manner. I'm sure we've all had to deal with shared folders that quickly became islands of misfit projects and files. And I know the last time I really needed to access and understand a project, there was no explanation of what the folder I was looking at contained.

Git, and storing your projects in repositories makes you think more about how others will need to use your work. It is extra work to manage projects to be fair, but this extra work will pay dividends.

GitHub, GitLab, and Bitbucket have become extremely popular hubs for organizing projects versioned with Git (and Mercurial, another version control system, in the case of Bitbucket). These hosting websites have made it very easy to create documentation surrounding products, via a 'Readme' file. More detailed documentation sites can also accompany projects and be hosted right alongside the project files themselves. This makes it easy to document anything from a small one-off project, to a complex multi-dimensional project. All within the same platform.

Let's revisit the project we started above for example. This project as it stands right now is just an Excel file and an Alteryx file. There is no explanation about what this project is for, what it does, or even how to configure it if it were to be moved, changed, etc. 

Let's change that!

First, add a Readme file to your local project:

![Add Readme File]({{site.baseurl}}public/img/10-readme.png)

Add a description of your project to your Readme file (in this case I just made something up):

![Readme Description]({{site.baseurl}}public/img/11-readme.png)

Add your Readme file to your tracked Git files:

`$ git add .`

Push your changes:

`$ git push -u origin master`

View in Gitlab:

![GitLab with Readme]({{site.baseurl}}public/img/12-readme-gitlab.png)

It's that easy! Now you can share your projects and track them with team members. And if you do your part, they'll have a descriptive document to guide them through how it works, why it's needed, and more.

The ability to store and revert changes, collaborate with colleagues easy on files, and organize projects using easy to access and navigate web based tools makes Git a winning choice for domains outside of or tangential to software development.
