---
title: 'Google Summer of Code 2019 : Work Report'
layout: post
date: 2019-08-20 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: GSoC 2019 - Work Report
---

![GSoC](https://developers.google.com/open-source/gsoc/resources/downloads/GSoC-logo-horizontal.svg)

<center>
<img src="https://miro.medium.com/max/1200/1*YJNS0JVl7RsVDTmORGZ6xA.png" width="40%"/>
</center>

---

My proposal for **Implementing Support for Different robots.txt Parsers in Scrapy** was selected as an official project under **Google Summer of Code 2019**. I worked with the organisation **[Scrapy](https://github.com/scrapy/scrapy)** under **Python Software Foundation**, under the mentorship of **Vostretsov Nikita** ([@whalebot-helmsman](https://github.com/whalebot-helmsman)) and **Adrián Chaves** ([@Gallaecio](https://github.com/Gallaecio)).

## Goal

[Scrapy](https://github.com/scrapy/scrapy) is a free and open source web crawling & scraping framework for Python. Scrapy internally uses Python's inbuilt robots.txt parser - [RobotFileParser](https://docs.python.org/3/library/urllib.robotparser.html) which is not fully specification compliant, but the more compliant alternatives are difficult to package and use within Scrapy’s pure-python development tree. The goal of my project was to introduce a new interface for parsers of robots.txt files, so that a better parser may be substituted as required or desired. The stretch goal of the project was to create a standalone pure-python robots.txt parser.

## Result

The primary and stretch goal of my project was achieved. I implemented a interface in Scrapy for robots.txt parsers, allowing Scrapy users to substitute a different parser. This interface was also implemented on top of third-party parsers - [Reppy](https://github.com/seomoz/reppy) and [Robotexclusionrulesparser](http://nikitathespider.com/python/rerp/), allowing Scrapy users to make the switch without having to write any wrapper code. The solution passed the existing test suite with Scrapy's default robots.txt parser, and both the third-party parsers. The related pull request [Scrapy/#3796](https://github.com/scrapy/scrapy/pull/3796) was merged on 2 Aug 2019.

I also created a pure-Python fully specification compliant robots.txt parser, which I named [Protego](https://github.com/scrapy/protego). Protego supports modern robots.txt conventions like wildcards, length based rule ordering, request rate, etc. Protego is also compatible with the new robots.txt specification draft proposed by Google. I benchmarked Protego to see how well it performs compare to popular existing parsers, and the results were impressive. Protego outperformed python based alternative [Robotexclusionrulesparser](http://nikitathespider.com/python/rerp/) - performing approximately 4x faster. Protego's performance was almost equal to [RobotFileParser](https://docs.python.org/3/library/urllib.robotparser.html) coming in just a little bit slower, but that is understandable as Protego does a lot more under the hood, and provides more features. More detailed benchmark results can be found [here](https://github.com/scrapy/scrapy/issues/3969#issue-482163200). Protego is now a part of Scrapy organisation on GitHub, and the latest version of Protego is on PyPI, hence it can be used by a simple ``pip install protego`` charm. The related pull request [Protego/#1](https://github.com/scrapy/protego/pull/1) was merged on 13 Aug 2019.

## Related Pull Requests and Commits

For my project, I worked on these two repositories on GitHub - [Scrapy/Scrapy](https://github.com/scrapy/scrapy) and [Scrapy/Protego](https://github.com/scrapy/protego). Here are the pull requests authored by me -

  * [Scrapy/#3796](https://github.com/scrapy/scrapy/pull/3796) - Implementing a interface for robots.txt parsers in Scrapy.
  * [Protego/#1](https://github.com/scrapy/protego/pull/1) - Initial release of Protego.

## Work in the Pipeline

I have submitted a pull request [Scrapy/#3935](https://github.com/scrapy/scrapy/pull/3935) - adding support for Protego in Scrapy. It is currently in the review phase. I have initiated a discussion on making Protego the default robots.txt parser in Scrapy. I am eager to hear the response from developers and users of Scrapy on Protego, and whether they feel it is ready for it or not. Here are the pull requests/issues I will work on post GSoC -

  * [Scrapy/#3935](https://github.com/scrapy/scrapy/pull/3935) - Adding support for Protego in Scrapy.
  * [Scrapy/#3969](https://github.com/scrapy/scrapy/issues/3969) - GitHub issue to make Protego the default robots.txt parser in Scrapy.

## Learnings

  I think the most important take away was that - you don't need to know the entire codebase of a project to make contributions (even significant ones). Scrapy probably has the largest codebase among everything I have every worked on. This is a misconception a lot of people have. Just two weeks back, I received an email from someone asking me how I was able to contribute to Scrapy, and how I learned Scrapy's codebase and how much time it took. He was surprised when I told him that I still don't know what the majority of Scrapy's code does, and to be honest, I have no idea how Scrapy schedules requests, how twisted works or what deferred is. I also learned about profiling, asynchronous programming, and wheels. I learned to work with Travis. I learned that implementation of Python's builtin modules are actually quite simple.

  The goal of Google Summer of Code is to introduce students to open source software development. It does that job very well. I feel more confident as a developer now, and I am willing to contribute more. In fact, I have started contributing to other open source projects as well. For quite some time now, I have been working to add CUDA support to [GoCV](https://github.com/hybridgroup/gocv) (Golang based wrapper around OpenCV). I am also working to add support for hardware accelerated image processing in [Darkroom](https://github.com/gojek/darkroom) (Golang based image proxy). GSoC is an amazing learning experience.

## Conclusion

I have no words to describe how grateful I am to my mentors - **Vostretsov Nikita** and **Adrián Chaves** - for all their support and for being extremely responsive and helpful with every one of my problems. I am also thankful to **Scrapy** and **Google** for the opportunity to work on this project, which helped me learn a lot in such a short period of time. My GSoC experience has surely increased my confidence as a developer. 