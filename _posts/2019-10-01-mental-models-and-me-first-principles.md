---
layout: post
title: Mental Models and Me - First Principles 🚀
date: 2019-10-01T07:42:50.664Z
description: This is a series on Mental Models I'm writing to help me understand how they work, and how I can use them to improve my choices. 
categories: thoughts
tags:
  - mental models
excerpt_separator: <!--more-->
---

You’ve likely encountered the idea and use of Mental Models if you’ve done some reading about Jeff Bezos or Elon Musk.

<!--more-->

<img src="https://media.giphy.com/media/BmmfETghGOPrW/giphy.gif" alt="math-gif" />

If you have no idea what they are, I’ll explain. 

In short <a href="https://en.wikipedia.org/wiki/Mental_model">Mental Models</a> are ways to look at systems, and they will help you solve problems by making better decisions. 

All things you do in life revolve around making decisions based on systems. A system can be a business like Amazon, a tool like a car, a process like an assembly line, or a state of being like your health. Mental Models will help you do a better job making decisions involving systems by breaking problems down into smaller chunks, or organizing facts in ways that help you use reasoning skills to make more informed decisions.

If you want a more detailed and thorough explanation, I suggest you read this write-up about <a href="https://www.julian.com/blog/mental-model-examples">Mental Models</a> by Julian Shapiro. He’s done an excellent job of explaining what Mental Models are and how you can use them.

## First Principles

### Definition

First Principles, or reasoning from first principles, is the process of breaking down a problem into its most base level components that you know to be true, and building up from there. 

To explain First Principles, who better to do the explaining than the most prolific proponent of them today, Elon Musk. We can see him explain First Principles in the context of discussing his inspiration for creating SpaceX.

<iframe width="560" height="315" src="https://www.youtube.com/embed/NV3sBlRgzTI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

“Physics teaches you to reason from first principles rather than by analogy. So I said, okay, let’s look at the first principles. What is a rocket made of? Aerospace-grade aluminum alloys, plus some titanium, copper, and carbon fiber. Then I asked, what is the value of those materials on the commodity market? It turned out that the materials cost of a rocket was around two percent of the typical price.” — Elon Musk

## How to Use First Principles

To utilize first principles I like Julian Shapiro’s approach of periodically asking yourself questions about the underlying systems that are involved in a problem.

Start with identifying the type of system you’re woking with (a business, process, tool, etc.), then ask yourself if the system is already efficient. If not, what underlying principles does it rely on, and could you restart from those principles to recreate and run a better system.

The best solution to a problem is not where everyone is already looking.

Let’s walk through a quick example.

Cooking is a common activity that can commonly be boiled down to its core principles. Many people like to approach cooking by looking at a recipe and assembling the ingredients listed. But if your food options are limited, and you aren’t going to the store, you can see how that approach limits what you’re able to make. 

A recipe is really just a system. So are the ingredients. Every recipe is a process (add 3 of x, add 1/2 of y). And every ingredient is just a tool, for example an egg can be cooked in <a href="https://www.thedailymeal.com/cook/50-ways-cook-egg-gallery">at least 50 different ways</a>. When we think of these things in this way, we can start to think about their core elements. This is how chefs can identify flavor combinations no one else has thought of, and why with only a few ingredients, chefs on television can make restaurant quality meals in under an hour. They have mastered first principles when it comes to cooking.

And with only a little bit of thought, you can probably manage to make something edible from ingredients you have at home.

Let’s assume we’re at home and we have the following ingredients in the pantry:

- Red Bell Pepper
- Spinach
- 3 Eggs
- Olive oil
- General spices (salt, pepper, garlic, onion powder)

Flipping through a recipe book will likely yield lots of recipes that require some of these ingredients, but not all of them, or, additional ones you don’t have access to. Instead of looking for a recipe that matches our ingredient list. Let’s look at the items we have, and build from there.

We could make:

- A spinach salad with bell peppers and hard boiled eggs
- Scrambled eggs with spinich and bell pepper
- Bell peppers stuffed with egg and spinach

Each of these uses one of our more core ingredients (egg, spinach, bell pepper) as a base for a dish that will work, despite not having all the ingredients required by a recipe book. We can even season them with olive oil and basic spices for flavor. And we didn’t have to make a run to the store!

This is first principles in action. Many people cannot cook like this because they look at a pantry and see a lack of recipes, not a collection of possible ingredients.

## How I’m Using First Principles

In my own life I use first principles to do more with less. One obvious example is in how I’ve not paid a single dime for hosting on any of my content websites for over 6 years!

I was paying somewhere around $40 a month 6 years ago to host around 5-6 small projects. Only one of which was making a little bit of money. Being in college at the time, that was a good amount of coin going out the door every month, and it made me want to scale back on projects. I knew there had to be something I could do to reduce my bill.

My first thought was to host these websites all on the same server, like a $5 ‘droplet’ VPS from Digital Ocean. But that would mean figuring out how to migrate some WordPress sites, NodeJS apps, and a Ruby on Rails application to the same server. And what would that mean for the web traffic I was getting, would there be slowdowns?

Then, I thought about what each site was fundamentally doing. A website is just a system. And so is a web host.

Each website was at its core a content site. Spoiler, they were all essentially blogs.

Doing some research at the time led me down a path to ’Static Site Generators’. Essentially most content sites at the time were running on server based website CMS technology (WordPress, Drupal, etc.). Which meant that a server was ‘serving’ up dynamic content when hosted on a server. This costs money. And was costing me money. But static site generators were different. They compiled your site, and let you instead focus on hosting just the static assets. Which was all I needed for these particular sites.

I migrated my WordPress sites to Jekyll (a static site generator), and hosted my websites for free using Amazon S3, and later GitHub Pages.

—

Thanks for reading, if you enjoyed that please follow me on <a href="https://twitter.com/notcolinn">Twitter</a>. 

### Next week: Margin of Safety ➡️
