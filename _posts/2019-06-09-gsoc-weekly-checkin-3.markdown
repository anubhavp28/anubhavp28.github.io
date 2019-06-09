---
title: 'GSoC 2019 : Weekly Check-in #3'
layout: post
date: 2019-06-7 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

Hello, wandering pythonistas! The second week of GSoC coding period is coming to an end. Here is an update on what I achieved in the past week and what I am looking forward to.

## What did you do this week?

* I made few changes to the interface according to the feedback received from the mentors.

* I implemented the interface on top of third party parsers like [Robotexclusionrulesparser](http://nikitathespider.com/python/rerp/) and [Reppy](https://github.com/seomoz/reppy).

* Wrote tests for testing the implementation of interface on top of the two parsers. This was a little tricky. We don’t want our implementation to change any behaviour of the parser. We have to make sure that behaviour of the parser was is irrespective of whether it is called using the interface or it is called directly. That meant finding and considering all possibilities for test case including corners cases.  

* Modified Scrapy to use the new interface (instead of directly calling Python’s inbuilt [RobotFileParser](https://docs.python.org/3/library/urllib.robotparser.html)).

* I had the weekly meeting with my mentors, where we discussed new stretch goals for the project.

## What is coming up next?

It will depend on the feedback of the mentors. If everything seems good to them, I will focus my attention on writing a pure python `robots.txt` parser.

## Did you get stuck anywhere?

Nothing major, though I had little difficulty due my lack of knowledge of difference between Python 2 and Python 3. I knew Python 3 uses unicode string by default, what I didn’t know is that in Python 3 `bytes` and `str` type are different. Hence, encoding a string produces an object of type `bytes`. This actually makes sense, having different types for string and arbitrary binary data.      