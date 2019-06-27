---
title: 'GSoC 2019 : Weekly Check-in #4'
layout: post
date: 2019-06-14 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

Hello! The third week of GSoC coding period is coming to an end. Here is an update on what I achieved in the past week and what I am looking forward to.

## What did you do this week?

* Created separate tox testing environments for testing integration with third-party parsers like [Robotexclusionrulesparser](http://nikitathespider.com/python/rerp/) and [Reppy](https://github.com/seomoz/reppy).

* Made Travis use the new tox environments.

* Described these parsers in Scrapy documentation.

* Got [Robotexclusionrulesparser](http://nikitathespider.com/python/rerp/) to work with unicode user agents.

## What is coming up next?

I will be working on creating a python based `robots.txt` parser which compliant with spec and supports modern conventions.

## Did you get stuck anywhere?

Nothing major.  