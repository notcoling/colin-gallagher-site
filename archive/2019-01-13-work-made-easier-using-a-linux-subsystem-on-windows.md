---
layout: post
title: 'Work Made Easier: Using a Linux Subsystem on Windows'
date: 2019-01-12T01:29:00.000Z
description: >-
  What Windows Subsystem for Linux is, how it works, and how it can make you
  more productive if you use Windows 10 at work.
categories: 
tags:
  - windows
  - linux
  - productivity
excerpt_separator: <!--more-->
---
# Using a Linux Subsystem on Windows

At work I sometimes find myself struggling to feel productive. And not because I’m distracted by social media, or because I forgot to have a cup of coffee. Mostly it’s because we use Windows, and a lot of the productivity tricks I’ve learned over the years are only good on Linux or UNIX based operating systems.

<!--more-->

Being able to do things like spinning up a website or using the command line to automate some tedious task. It’s just more difficult on Windows.

And I’m no stranger to Windows. I use Windows as a daily driver for things like gaming, VR, music production, and more. The fact of the matter is, Windows doesn’t perform as well as a scripting or development environment.

But Microsoft has recently added a cool feature to Windows 10 that has made work a lot less tedious for me. The Windows Subsystem for Linux or WSL.

# What is the Windows Subsystem for Linux?

WSL is a compatibility layer for running Linux binaries natively in Windows 10 (and Windows server 2019). Letting you run a Linux kernel interface directly in Windows, allowing you access to your favorite Linux distros (like Ubuntu, Debian, openSUSE, and more) without a VM.

According to the [Microsoft Docs on WSL](https://docs.microsoft.com/en-us/windows/wsl/about), all of this allows you to:

* Select a GNU/Linux distribution from the Windows Store
* Run common command-line software such as grep, sed, awk, or other ELF-64 binaries
* Run Bash shell scripts and GNU/Linux command-line applications like:
  * Tools: vim, emacs, tmux
  * Languages: Javascript/node.js, Ruby, Python, C/C++, C# & F#, Rust, Go, etc.
  * Services: sshd, MySQL, Apache, lighttpd
* Install additional software using own GNU/Linux distribution package manager
* Invoke Windows applications using a Unix-like command-line shell
* Invoke GNU/Linux applications on Windows (including graphical applications)

WSL is by far the best way to run Linux applications on Windows. 

# How can WSL be Useful?

WSL allows me to use the software that I want to use, without having to use a virtual machine, or dual boot Windows and Linux. This saves me time and allows me to spend less time tinkering with VMs. It also provides for the kind of functionality that was just not available in VMs at all, or required hours of setup, like being able to access the same file system from both operating systems or running graphical Linux applications.

This has made creating small websites or creating quick scripts much more comfortable. No longer do I have to maintain a separate development-oriented environment. Instead, I can quickly open up Ubuntu from Windows, and dive into my projects.

I’d estimate I save at least 2 hours each week by being able to use WSL instead of a standalone VM, Vagrant, Docker, or any other competing solutions available to provide Linux functionality on Windows.

# Getting Started With WSL

Setup for WSL is a breeze. Microsoft does a great job giving [instructions in their documentation](https://docs.microsoft.com/en-us/windows/wsl/install-win10). But I’ll go over the Windows 10 installation process briefly here as well.

## Installing the Windows Subsystem for Linux

To install, you’ll need to enable the "Windows Subsystem for Linux" feature. The easiest way to do this is to open PowerShell as Administrator and run:

```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

Then, restart your computer when prompted.

Choose Your Linux Distro, download it, and Install

There are three ways to choose and download a Linux distribution for WSL:

* You can download and install a distro from the Windows Store
* Download and install it from the Command-Line or a Script
* Download and manually unpack and install

The easiest way is to open the Microsoft Store and choose your favorite Linux distribution. The choices available as of writing this post are:

* Ubuntu
* OpenSUSE
* SLES
* Kali Linux
* Debian GNU/Linux

![Linux Distros in the Microsoft Store - Source Microsoft Docs]({{site.baseurl}}public/img/store.png)

Once you’ve chosen your distribution and navigated to its page, you can select "Get", and the distribution will be downloaded and installed.

![Ubuntu Page in the Windows Store - Source Microsoft Docs]({{site.baseurl}}public/img/ubuntustore.png)

Now that your Linux distro is installed, you must initialize your new distro instance once, before it can be used.

## Configure Your Linux Distribution

To finish the installation of your newly installed Linux distro, you will need to launch an instance of it. This can be done in the Windows store. 

This will open a console that will prompt you to create a user account. This user account is for the normal non-admin user that you'll be logged-in as by default when launching a distro. You can choose any username and password you wish - they have no bearing on your Windows username.

![Ubuntu user configuration in WSL - Source Microsoft Docs]({{site.baseurl}}public/img/ubuntuinstall.png)

When you open a new distro instance, you won't be prompted for your password, but if you elevate a process using sudo, you will need to enter your password, so make sure you choose a password you can easily remember! See the User Support page for more info.

## Update & Upgrade your Distro's Packages

Most distros ship with an empty/minimal package catalog. We strongly recommend regularly updating your package catalog, and upgrading your installed packages using your distro's preferred package manager. On Debian/Ubuntu, you use apt:

```
sudo apt update && sudo apt upgrade
```

Windows does not automatically update or upgrade your Linux distro(s): This is a task that the Linux users prefer to control themselves.

## You’re all set!

![Up and running with WSL! - Source Microsoft Docs]({{site.baseurl}}public/img/linux-on-wsl.png)

WSL is excellent for someone like me, required to use a Windows machine at work, but who needs access to Linux based programs and tools. Having easy access to these at work allows me to do things that would typically be tricky on a Windows 10 machine like:

* Creating GatsbyJS websites using NodeJS
* Python scripting for data analysis and productivity
* Using command line utilities and tools

This is yet another great feature from Microsoft, and I would encourage everyone currently using a VM or similar solution for tasks like these, to use WSL. WSL in addition to VSCode, the acquisition of GitHub, and others have been great moves for Microsoft, and I hope there is more to come!
