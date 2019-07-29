---
layout: post
title: Customizing Windows Subsystem for Linux (WSL)
date: 2019-01-30T05:54:00.000Z
description: >-
  Windows Subsystem for Linux is awesome. But the default Windows 10 colors for
  the terminal window are not. How do we go about fixing that?
categories: 
tags:
  - windows
  - linux
  - design
excerpt_separator: <!--more-->
---
Windows Subsystem for Linux is a fantastic way to use Linux within Windows 10. I explain how to get started with WSL in a previous blog post, [found here](https://colingallagher.me/blog/2019-01-13-work-made-easier-using-a-linux-subsystem-on-windows/). However, once you are up and running with WSL, you might notice that the default Windows 10 color scheme leaves a lot to be desired regarding usability.

<!--more-->

The default colors include a dark blue, that is hard to read on the black console background. And this color can't be properly changed using the built-in Windows 10 properties menu.

![Windows 10 terminal properties menu]({{site.baseurl}}public/img/windows-10-terminal-properties.png)

Instead, we'll need to use our `.bashrc` file to change the colors. This file can be found in the home directory of your Linux distro (I'm running Ubuntu).

This may come as a relief if you're already used to editing your bash prompt. But if you aren't, I'll go over everything we need to get the colors changed to something more pleasing to the eye.

# Changing our Bash Prompt

Changing the bash prompt is relatively simple and straight forward. We need to update the default colors used by bash, and we can also improve how the default prompt looks (to fit your personal preferences).

First and foremost we need to update the colors so we can be rid of that hard to read, and hard on the eyes blue that is used by default.

![Windows 10 default terminal colors]({{site.baseurl}}public/img/windows-10-default-prompt.png)

## Modifying the Colors of our Bash Prompt

Changing the prompt can be done using these variables, which you can read more about [here](https://unix.stackexchange.com/questions/124407/what-color-codes-can-i-use-in-my-ps1-prompt). By using these colors we can override the defaults used by WSL and Bash.

We'll need to add 2 lines to our `.bashrc` file in order to modify the default colors. The first line (a very long line of mostly numbers) overrides the default colors of the prompt with various other colors (in this case mostly purple). The second line makes our colors available to bash and our Linux terminal.

```
LS_COLORS='rs=0:di=1;35:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:su=37;41:sg=30;43:ca=30;41:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.tar=01;31:*.tgz=01;31:*.arj=01;31:*.taz=01;31:*.lzh=01;31:*.lzma=01;31:*.tlz=01;31:*.txz=01;31:*.zip=01;31:*.z=01;31:*.Z=01;31:*.dz=01;31:*.gz=01;31:*.lz=01;31:*.xz=01;31:*.bz2=01;31:*.bz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tz=01;31:*.deb=01;31:*.rpm=01;31:*.jar=01;31:*.war=01;31:*.ear=01;31:*.sar=01;31:*.rar=01;31:*.ace=01;31:*.zoo=01;31:*.cpio=01;31:*.7z=01;31:*.rz=01;31:*.jpg=01;35:*.jpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.axv=01;35:*.anx=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.axa=00;36:*.oga=00;36:*.spx=00;36:*.xspf=00;36:';
```

```
export LS_COLORS
```

![Windows 10 prompt with new colors]({{site.baseurl}}public/img/windows-10-new-prompt.png)

Now our terminal is more readable, with that hard to read blue, and other colors replace with colors like a light purple, cyan, and others!

## Changing the Text of our Bash Prompt

The default bash prompt given with the WSL install is not bad. All of the info is pertinent and is displayed in a way that doesn't take up too much extra real estate on the screen.

But because I'm not planning on doing a lot of remote development, I'm going to opt for a prompt that displays only the current working directory alongside my username. Below is the line we need to add to the `.bashrc` file in order to change the prompt.

```
PS1='\e[37;1m\u@\e[35m \w \e[0m\$ '
```

Once that is appended to the `.bashrc` file you are all ready to go!

# Making our Changes Available in VSCode

Now, because I also like to edit in VSCode, and not just Vim, or Emacs inside of a terminal window (I'm not that `1337`), so there is still another additional step.

When running Linux inside of a virtual machine, Vagrant, Docker, or some other configuration, it is tough to get VSCode to work nicely within Windows 10. Being able to edit files directly from within the host operating system is possible, but doesn't quite feel native, and certainly is not conducive to productivity. You can see an example of how cumbersome it can be in [this article](https://medium.com/@prtdomingo/editing-files-in-your-linux-virtual-machine-made-a-lot-easier-with-remote-vscode-6bb98d0639a4) about remote VSCode.

But making our new WSL bash environment available in the VSCode terminal is as easy as entering just one command:

```
bash
```

![Windows 10 WSL and new prompt in VSCode terminal]({{site.baseurl}}public/img/windows-10-vscode-prompt.png)

<div style="width:100%;height:0;padding-bottom:67%;position:relative;"><iframe src="https://giphy.com/embed/xT0xeJpnrWC4XWblEk" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></div><br /><br />

And there you have it. Now we're up and running with WSL. And we have colors that are easy on our eyes, with our environment is customized the way we like it!
