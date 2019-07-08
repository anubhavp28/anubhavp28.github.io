---
title: 'Accepted for GSoC 2019 : 3 Months of Open Source Ahead'
layout: post
date: 2019-05-28 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

![Header](https://1.bp.blogspot.com/-T-jEcKc3EIc/XJVXUldWEJI/AAAAAAAAB4U/Mqk1-XPQ0LEuemA16SXUQ4gbeXwjiDFDwCLcBGAs/s1600/GSoC%2B-%2BVertical%2BWide%2B-%2BGray%2BText%2B-%2BWhite%2BBG.png
)

---

Hello! I have been selected as a student for Google Summer of Code 2019. For those of you who are unaware, [Google Summer of Code](https://summerofcode.withgoogle.com/) is a global program focused on bringing more student developers into open source software development. Students developers get an opportunity to work with an open source organization on a 3 month programming project.

I am working on [Scrapy](https://scrapy.org/) - an open-source scraping and web crawling framework. My task is to implement an interface for `robots.txt` parsers in Scrapy. The stretch goal of the project is to write a fully spec compliant pure python `robots.txt` parser.

This blog is part of a series of blog posts where I will go in depth to describe my work. Since, this is the first blog post, I have dedicated it to explain about my project. My project has a lot to do with `robots.txt` and [Robot Exclusion Standard](https://en.wikipedia.org/wiki/Robots_exclusion_standard). Let’s take a look at what these things are.

[Web crawlers](https://en.wikipedia.org/wiki/Web_crawler) (also called spiders) are bots that systematically browse the internet, generally for the purpose of extracting data (called scraping) or indexing. Search engines (eg. google) use web crawlers to index pages on the internet, this index is then used to serve users with relevant results.

When web crawlers visit a website, they too consume resources of the web servers, similar to a normal user. A crawler can make multiple requests per second. Therefore, unrestricted crawling can lower the performance of a website, and cause annoyance to its users. A solution to this problem is [robots exclusion standard](https://en.wikipedia.org/wiki/Robots_exclusion_standard), which makes it possible to specify which parts of the website a crawler should not access, and how frequently a crawler should make requests for a resource on the server. The standard allows websites to specify how “polite” a crawler should be.

Under [robots exclusion standard](https://en.wikipedia.org/wiki/Robots_exclusion_standard), instructions for crawlers are specified in a file named `robots.txt` placed at the root of the website. These instructions have to be specified in a certain format.

`robots.txt` standard is not owned by any standard body, and is not in active development since 1997. So, the standard has not been revised for more than two decades which, I will argue, had led it to become outdated. Meanwhile, search giants like google, bing, <s>yahoo!</s> have collaborated to create an informal extension of the standard which their crawlers adhere to. Since usually the majority of crawling requests originates from search engines, most web administrators write `robots.txt` adhering to the informal extension of the specification. 

Scrapy uses `RobotFileParser` (Python’s inbuilt `robots.txt` parser - [docs](https://docs.python.org/3/library/urllib.robotparser.html)), which strictly follows the old specification, and has not been updated. Hence, Scrapy is likely to misinterpret the crawling rules for majority of websites on the internet. There was an effort to switch to another parser, but since there isn’t a fully compliant pure python parser available, and it is difficult to package non-python code with Scrapy because its wide user base consisting of people using a wide variety of platforms and implementations of python. Including non-python code would need dropping the support of [pypy](https://pypy.org/), and would require users to install compilers for other languages (which may not be easy on every platform).

The short term solution to overcome this could be to allow users to switch to a different parser if they wish too, and keep `RobotFileParser` as the default in Scrapy. It has additional benefit of giving more power to the users. For this, we are planning to create an interface for `robots.txt` parsers in Scrapy, and implementing this interface on top few popular parsers. This the first goal of my project. In the end, we would like to have a fully spec compliant pure python parser which Scrapy could use by default. This is the stretch goal of my project.

Hope, to have an incredible 3 months ahead :smile:. If you need any help regarding Google Summer of Code or you just want to learn more about my work, feel free email me at <a href="mailto:anubhavp28@gmail.cpingom">anubhavp28@gmail.com</a>.