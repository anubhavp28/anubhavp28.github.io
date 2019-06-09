---
title: 'GSoC 2019 : Weekly Check-in #2'
layout: post
date: 2019-06-2 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

Hello everyone. The first week of GSoC coding period is coming to an end. Here is an update on what I achieved in the past week and what I am looking forward to.

## What did you do this week?

I submitted my first pull request related to GSoC. This week mostly involved discussion on interface specification. I learned that designing an interface involves considering several small but quite important details, and a good practice is to question every choice you make. Also, I had a meeting with my mentors where we discussed about weekly milestones and decided to have weekly meetings, every Tuesdays. I implemented the interface on top of Python’s in-built `robots.txt` parser and worked on documentation related to the interface.

I got an opportunity to deep dive into the source code of Python’s in-built `robots.txt` parser.  For some reason, I always had this belief that reading through the implementation of python (or any language) and its inbuilt modules, would be difficult and not really useful, and code would mostly be complex and cryptic (to a beginner like me). This doesn’t seem to be the case (at least with python). I should do more of this, looking at a module’s implementation for fun •ᴗ• .   

## What is coming up next?

In the next week, I am looking to finalize the interface, and modify Scrapy to use the interface to communicate with the parsers. I would also work on documenting the interface, and if time permits will implement the interface on top of few other parsers.

## Did you get stuck anywhere?

Nope. I learned a lot from constant feedback from my mentors. It was an awesome week •ᴗ• 