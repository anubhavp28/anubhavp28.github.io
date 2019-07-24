---
title: 'GSoC 2019 : Weekly Check-in #9'
layout: post
date: 2019-07-21 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

## What did you do this week?

* I added tests to make sure Protego doesn't throw exceptions on `robots.txt` of top 10,000 most popular websites.
Utilised Scrapy to create a tool to download `robots.txt` of top 10,000 most popular websites.

* Benchmarked Protego : I ran Protego (written in Python), Robotexclusionrulesparser (written in Python), Reppy (written in C++ but has Python interface) on 570 `robots.txt` downloaded from top 1000 websites, and here are the results.
  
   - Time spend parsing the `robots.txt`
       1. Protego : 79.00128873897484 seconds  
       2. Robotexclusionrulesparser : 0.30100024401326664 seconds
       3. Reppy : 0.05821833698428236 seconds

   - Time spend answering queries (1000 queries (all were identical) per `robots.txt`)
       1. Protego : 14.736387926022871 seconds
       2. Robotexclusionrulesparser : 67.33521732398367 seconds
       3. Reppy : 1.0866852040198864 seconds

* Added logging to Protego.

## What is coming up next?

* Will depend on the review from the mentors. If everything looks good to them, I would shift my focus back on Scrapy.

* Make `SitemapSpider` use the new interface for `robots.txt` parsers.

* Implement Crawl-delay & Host directive support in Scrapy.

## Did you get stuck anywhere?

Nothing major.