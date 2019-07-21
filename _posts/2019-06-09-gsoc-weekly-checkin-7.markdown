---
title: 'GSoC 2019 : Weekly Check-in #7'
layout: post
date: 2019-07-5 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

Hey! here is an update on what I have achieved so far.

## What did you do this week?

* Protego now passes all tests borrowed from reppy, rep-cpp and robotexclusionrulesparser.
  
* Made few changes to Protego to make it compatible with google's parser.
  
* Worked on changes suggest on the interface pull request.
  
* Wrote code to fetch robots.txt files from top 1000 websites, and generate statistics we need. ( [link](https://nbviewer.jupyter.org/github/anubhavp28/robotstxt_usage_stats/blob/master/Robotstxt_Stats.ipynb) )
  
* Looked at the code of Google's robots.txt parser for the purpose of creating a python interface on top of it. I might need to modify its code as currently it parses the robots.txt file for answering every query. (Working on anything in C++ that uses pointers or STL heavily makes me feel uncomfortable).

## What is coming up next?
* Modify protego to make it behave similar to Google's parser (will need to add few more features like record group merging), and add more tests.
  
* Document Protego.
  
* Benchmarking Protego's performance.
  
* I would need to read how to call C/C++ code from python, for creating an interface on top Google's parser. I am currently thinking of using Cython.
  
* Would work on blog posts (planning to write 3 blog posts within this week).

## Did you get stuck anywhere?
* No, I got to work with some data science tools like jupyter notebook & pandas.