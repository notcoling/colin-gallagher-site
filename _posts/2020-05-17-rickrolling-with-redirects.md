---
layout: post
title: Rickrolling with Redirects 👺
date: 2020-05-17T10:01:00.000Z
description: >-
  How to rickroll people who try to break into your website. A fun trick that's really simple to implement if you're hosting your website with Netlify.
categories: 
  - code
tags:
  - netlify
  - static sites
excerpt_separator: <!--more-->
---

I was inspired by this tweet 👇 from Liam Hammett to write a brief post on [rickrolling](https://en.wikipedia.org/wiki/Rickrolling) people who try to break into your site using common URLs.

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">🙃 Make sure to rickroll people trying to break into your site <a href="https://t.co/4cd80Pr9p9">pic.twitter.com/4cd80Pr9p9</a></p>&mdash; Liam Hammett (@LiamHammett) <a href="https://twitter.com/LiamHammett/status/1260984553570570240?ref_src=twsrc%5Etfw">May 14, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

A lot of websites use the same tech (Wordpress), and thus some of the same URLs are used for logins and admin pages. Which makes them easy targets for jerks.

With Wordpress those paths are most commonly:
- https://yoursite.com/wp-admin
- https://yoursite.com/wp-login.php

Luckily if your site is a static site, you don’t have to worry about those particular login URLs doing anything.

When I saw the above tweet from Liam, I thought it would be fun to put together my own version of the script for my site. I don't currently use a CMS on my live site so I'm including both the `/admin` and `/login` urls. If you have a live CMS you could exclude those.

![My _redirects Script](/public/img/post/2020-05-17-rickrolling-with-redirects/rickrolling-with-redirects-redirects.png)

This script uses [Netlify redirects](https://docs.netlify.com/routing/redirects/) in order to send people who visit these urls to the award winning 1987 debut single from Rick Astley that we all know and love. If you host your site with Netlify you can [add this script to the root of your site and do the same](https://docs.netlify.com/routing/redirects/#syntax-for-the-redirects-file).

You can see this in action by trying to go to [https://colingallagher.me/admin](https://colingallagher.me/admin)

![Rick Astley Dancing](https://media.giphy.com/media/Vuw9m5wXviFIQ/giphy.gif)
