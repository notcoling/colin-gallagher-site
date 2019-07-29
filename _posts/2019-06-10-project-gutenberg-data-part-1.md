---
layout: post
title: 'Project Gutenberg Data: Part 1'
date: 2019-06-10T14:19:58.875Z
description: Is there anything to be learned from looking at Project Gutenberg data? Project Gutenberg offers over 59,000 free eBooks online in a wide variety of formats (PDF, HTML, ePub, Kindle, etc.). They offer some of the greatest literature the world has to offer, with focus on older works for which U.S. copyright has expired. “Thousands of volunteers digitized and diligently proofread the eBooks, for enjoyment and education.“
categories: 
tags:
  - data
excerpt_separator: <!--more-->
---
## What is Project Gutenberg?

Is there anything to be learned from looking at Project Gutenberg data?

[Project Gutenberg](https://www.gutenberg.org/) offers over 59,000 free eBooks online in a wide variety of formats (PDF, HTML, ePub, Kindle, etc.). They offer some of the greatest literature the world has to offer, with focus on older works for which U.S. copyright has expired. “Thousands of volunteers digitized and diligently proofread the eBooks, for enjoyment and education.“

<!--more-->

It’s a wonderful project that makes it easy to get classic works of literature, and other books, all online, and entirely free.

What’s not to love? You can download books in any format that you’d like and most of the books on Project Gutenberg are actually edited and formatted quite well. About the same quality you can expect from other online book retailers.

I use Project Gutenberg all the time. Usually when I’m looking to start reading something new, or revisit something old that I can’t remember if I have a copy of in storage somewhere. 

Upon browsing the site and looking at the top 100 books and authors, I wondered if there was any data available on the usage of Project Gutenberg, or trends in the consumption of books on the site. After all, this would be a great opportunity to see what gets read from this project. I couldn’t find anything like I was imagining online. I searched Project Gutenberg, Reddit, Kaggle, and everywhere else I could think of, and still I didn’t see any analysis of Project Gutenberg beyond the list of top books and authors (provided by Project Gutenberg). So, I decided to start thinking about putting together my own brief analysis, using data that I would have to compile.

## Starting to Explore Project Gutenberg

Which I guess first begins with the question, who uses Project Gutenberg? In order to answer that question, I looked to [Alexa](https://www.alexa.com/siteinfo) and [SimilarWeb](https://www.similarweb.com/). Both sites indicated similar things.

Many visitors have an interest in Literature (and other similar topics, no surprise there)
.

![Alexa Site Interests]({{site.baseurl}}public/img/alexa-site-audience-interests.png)

![SimilarWeb Topics]({{site.baseurl}}public/img/similarweb-topics.png)

![SimilarWeb Audience Interests]({{site.baseurl}}public/img/similarweb-audience-interests.png)

Search interest in classics (i.e. A Christmas Carol)
 gives Project Gutenberg a unique advantage in search. The books really are free, and the collected works on the site are almost certainly used in classes, leisure, and other activities. Which means that their performance in natural search will continue to perform. And we can see that it has performed quite well.

![SimilarWeb Search]({{site.baseurl}}public/img/similarweb-search.png)

![Alexa Top Keywords]({{site.baseurl}}public/img/top-keywords.png)

![SimilarWeb Organic vs. Paid]({{site.baseurl}}public/img/similarweb-organic-v-paid.png)

Project Gutenberg has a high Alexa site ranking (especially in US)
.

![SimilarWeb Rank]({{site.baseurl}}public/img/similarweb-rank.png)

![Alexa Rank]({{site.baseurl}}public/img/alexa-rank.png)

High overlap with other free book offerings (competitor sites audience overlap)
.

![Alexa Audience Overlap]({{site.baseurl}}public/img/alexa-audience-overlap.png)

![Alexa Audience Overlap by Site]({{site.baseurl}}public/img/alexa-similar-websites.png)

Social Traffic from highly engaged sources like Reddit
.

![SimilarWeb Social1]({{site.baseurl}}public/img/similarweb-social.png)

![SimilarWeb Social2]({{site.baseurl}}public/img/similarweb-social-detail.png)

High amounts of 'direct traffic' which may indicate repeat users, or knowledge of the site beyond referrers. Although, given this is a volunteer project, referred traffic may not be collected properly.

![SimilarWeb Traffic Sources]({{site.baseurl}}public/img/similarweb-traffic-sources.png)

Also, Project Gutenberg receives a high amount of referrals from Wikipedia.

![SimilarWeb Referring Sites]({{site.baseurl}}public/img/similarweb-referring-sites.png)

With a basic understanding (and I mean basic), I wanted to dive into some of the data and discover more about my favorite book site. What gets read the most over the course of a year? What authors get read the most? Are there any trends like popular time periods, popular categories, etc.? Do trends appear during certain times of year? There are lots of things that could be explored.

The only question I had was, could it be explored? And thankfully, the answer is yes! 

## Scoping The Project

What kind of data is available? Project Gutenberg makes available some basic statistics about what is popular on their [top 100 page](https://www.gutenberg.org/browse/scores/top). You can see (in order and quoted directly from the top 100 page) Top 100 EBooks yesterday, Top 100 Authors yesterday, Top 100 EBooks last 7 days, Top 100 Authors last 7 days, Top 100 EBooks last 30 days, and Top 100 Authors last 30 days.

Other data is available on the site (like download counts per book, 'bibrec' data, etc.), and could be accessed via scraping. However, I don’t want to set up a scrape because this project asks kindly not to do that, and they’ve provided so much value by making vast amounts of human knowledge freely available online. I’m choosing to respect their request.

That doesn’t mean we can’t get any data though! The top 100 section contains enough to work with. But if I want to work back a year (or more) to identify trends, Project Gutenberg sadly does not keep that data.

Fear not (again) as we can access it using [Archive.org’s Wayback Machine](https://archive.org/web/)! This is a great tool that lets you view snapshots of websites going back in time. And people have been kind enough to capture semi regular snapshots of Project Gutenberg! 

The snapshots are not precisely regular, but we can get within the first week of every month. So, for this analysis, we’ll plan on pulling data on the top 100 ebooks and authors per month for every month going back to June of 2018. Each pull will give us (roughly) the previous months data (top books and authors). This should be enough data to identify trends. However, we’ll also need metadata about the books.

Project Gutenberg does make some data available for classifying each book. They provide book details in RDF format. However, given the format of the data (subfolders, individual files) I’ll have to do some wrangling to make it usable.

For organizing and evaluating the data, I’ll be using a combination of visualization tools, which I’ll expand on in the next post.

## What's Next?

In Part 2 we'll dive into the data, some insights, and visualizations. I'll show the process I used to put the data into a useable format, and combine different data sources to try and extract meaning from the top 100 section of Project Gutenberg.

To be continued...
