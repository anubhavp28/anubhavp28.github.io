---
title: 'GSoC 2019 : Weekly Check-in #12'
layout: post
date: 2019-08-9 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

## What did you do this week?

* Benchmarking Protego (again). This time we crawled multiple domains (~1,100 domains) and downloaded links to pages as the crawler encounter them. We downloaded 111, 824 links in total.
Next we made each robots.txt parser - parse and answer query (we made parsers answer each query 5 times) in an order similar to how they would need to in a broad crawl. Here are the results :

    * Protego :
      * 25th percentile : 0.002419 seconds
      * 50th percentile : 0.006798 seconds
      * 75th percentile : 0.014307 seconds
      * 100th percentile : 2.546978 seconds
      * Total Time : 19.545984 seconds

    * RobotFileParser (default in Scrapy) :

      * 25th percentile : 0.002188 seconds
      * 50th percentile : 0.005350 secondsstyle
      * 75th percentile : 0.010492 seconds
      * 100th percentile : 1.805923 seconds
      * Total Time : 13.799954 seconds

    * Rerp Parser :
  
      * 25th percentile : 0.001288 seconds
      * 50th percentile : 0.005222 seconds
      * 75th percentile : 0.014640 seconds
      * 100th percentile : 52.706880 seconds
      * Total Time : 76.460496 seconds

    * Reppy Parser :
  
      * 25th percentile : 0.000210 seconds
      * 50th percentile : 0.000492 seconds
      * 75th percentile : 0.000997 seconds
      * 100th percentile : 0.129440 seconds
      * Total Time: 1.405558  seconds

* Removing an hack used in Protego due to lack of an option to ignore characters in `urllib.parse.unquote`. Added few new features to Protego as well. 

* Protego has been moved to Scrapy organisation.

## What is coming up next?

* Configuring Travis to push to PyPI automatically.

* Introducing a new `ROBOTSTXT_USER_AGENT` setting in Scrapy.

* Making `SitemapCrawler` use the new interface.

## Did you get stuck anywhere?

I got blocked by StackExchange for few hours.  I think they don't like crawlers on their websites. "It is a temporary automatic ban that is put up by our HAProxy instance when you hit our rate limiter." they answered to one of the questions on their website.