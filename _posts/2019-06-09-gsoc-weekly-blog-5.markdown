---
title: 'Need for Speed :car:'
layout: post
date: 2019-07-22 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

Hey! This is my fifth blog post for GSoC 2019, covering week 7 and 8.

The most of week 7 was spent making Protego compatible with Google's parser. I also worked on the documentation, since Protego codebase is small enough, proper comments and a good readme was sufficient. I uploaded Protego to PyPI - `pip install Protego` that's all it takes to install Protego. 

Week 8 was quite interesting. For Protego to become default in Scrapy, it is necessary that it doesn’t throw any kind of error while parsing `robots.txt` files. To make sure that, I decided to download `robots.txt` from top 10,000 websites. I added tests to see if Protego throws any exceptions while parsing the downloaded `robots.txt`. I benchmarked Protego, and the results were quite disappointing. You can see the result [here](https://anubhavp28.github.io/gsoc-weekly-checkin-9/). 

We decided to spend the next week improving performance of Protego. I am going to try profiling and heuristics, and see if the performance can be improved.