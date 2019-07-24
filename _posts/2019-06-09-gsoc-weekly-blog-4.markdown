---
title: 'Google open-sourced its robots.txt parser :rocket:'
layout: post
date: 2019-07-09 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

Hey! This is my fourth blog post for GSoC 2019, covering week 5 and 6.
 
Few interesting things have happened, Google has open-sourced its `robots.txt` parser, and have also taken the lead role in pushing the community and enterprises to create an official specification for `robots.txt`. I spend a good amount of time making Protego compatible with Google’s parser. This required rewriting a good chunk of Protego to support Google’s parser specific things such as merging record group, supporting misspellings, etc.
 
I am scared of reading or writing C++ code that uses STL or pointers heavily. So really going through the source code of Google’s parser was kind of uncomforting, but I was able to understand a good chunk of it, after a few days of struggle. 
 
Next up, I will work on making Protego 100% compatible with Google’s parser. I will have to document Protego. I will collect robots.txt from top 1000 websites to understand usage patterns.
