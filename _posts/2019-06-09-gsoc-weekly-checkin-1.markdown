---
title: 'GSoC 2019 : Weekly Check-in #1'
layout: post
date: 2019-05-23 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

Hey everyone. I am Anubhav, and this summer I am working to implement an interface for `robots.txt` parsers in Scrapy. This is the first of many upcoming weekly blog posts where I will describe in brief the work I have done in the previous week and my plans for the upcoming week. So, let's get started. 

## What did you do this week?

Most of time was spent on configuring a local development environment, and learning to use tox and how to run tests locally. For the patches I have submitted before, I didn't run tests locally beforehand, and relied solely on CI to do it. Running tests locally could have saved a lot of time. Also, I went through scrapy contribution guide, learned about twisted (scrapy uses it heavily) and PEP8, and worked on a pull request I had opened before.   

## What is comping up next?

*     I will have my first meeting with mentors of the project.
*     I will work on few pull requests I had opened before.
*     Maybe, since this is the last week of community bonding period, looking to have discussion with the mentors regarding interface specification.

## Did you get stuck anywhere?

I had minor difficulties understanding how to run tests using `tox`. When I followed the instructions given in scrapy documentation to run tests, I could only run tests using a Python 2.7 environment. Thankfully, `tox` has an incredible documentation that allowed to me understand settings inside of `tox.ini` config file. In the end, I just had to make few edits to my `tox.ini` file, and I was able to run tests using a Python 3 environment as well.