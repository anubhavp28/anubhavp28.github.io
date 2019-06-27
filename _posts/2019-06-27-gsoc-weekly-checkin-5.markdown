---
title: 'GSoC 2019 : Weekly Check-in #5'
layout: post
date: 2019-06-21 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

Hello! The fourth week of GSoC coding period is coming to an end. Here is an update on what I achieved in the past week and what I am looking forward to.

## What did you do this week?

* Implemented minor changes suggested by scrapy maintainers.

* Started working on a new pure python `robots.txt` parser, which lives [here](https://github.com/anubhavp28/protego) currently. It will eventually be moved to Scrapy organisation.

* Implemented support for standard `robots.txt` directives in the new parser.

* Integrated the code with `pytest` and `tox` for testing.

* Integrated the repo with Travis CI to trigger tests automatically on pull requests.

## What is coming up next?

* Implement support for modern conventions like wildcard matching, clear-param etc.

* Add a lot of tests (mostly borrowed from existing parsers).

* Performance benchmarking of the new parser (against existing parsers).

* Collecting statistics related to use of `robots.txt`. On suggestion of a mentor, I am planing to use `robots.txt` files of top 1000 websites in alexa rankings, and collect stats such as how many of them use `robots.txt`, how many records on average a record group contain, how many times a certain directives is mentioned, etc. This could help use make better choices for improving performance - such as whether to use a trie for prefix matching, etc.  

## Did you get stuck anywhere?

Oh, actually naming the parser was the hardest part   . I am still not satisfied with the name. I just ran out of ideas.

