---
title: 'GSoC 2019 : Weekly Check-in #6'
layout: post
date: 2019-06-28 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

Hello! It has been more than a month since the beginning of GSoC coding period, and I am completely satisfied with my progress. I am glad that I choose to work remotely this summer, since it has been raining heavily for last 5-6 days in Mumbai (place where I live). :smile:

## What did you do this week?

* Implemented support for wildcard matching and `request-rate` directive.

* Increased the number test cases, some of them were borrowed from `rep-cpp`, another `robots.txt` parser. The new test cases now ensure that the parser behaviour conforms to the google specification for `robots.txt`.

PS: I really overestimated the amount of work I would be able to do in a week while writing the last check-in - [Hofstadter's law](https://en.wikipedia.org/wiki/Hofstadter%27s_law).

## What is coming up next?

* Google open-sourced their `robots.txt` parser - here. Since Google is the most popular search engine in the world, it is likely that for most websites, the largest percentage of crawling requests they receive originates from Google. Hence, there out be more robots.txt written for Google's crawler than any other crawler. It would make sense to make Protego behave in a similar way to Google's parser.

* Documenting Protego.

* Increasing the number of test cases (we can borrow some from Google's parser).

* Benchmarking Protego's performance against other parsers.
Regarding the collecting statistics on robots.txt usage, I am not completely sure if it would be a good idea to invest time into it, now that I have found a blog, which describes the popularity of individual directives, and could help us prioritise which ones to implement. 

## Did you get stuck anywhere?

Nothing major. I found it simpler than I had initially expected.     