---
title: 'We are going faster than I predicted :bullettrain_side:'
layout: post
date: 2019-06-8 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

Hey, welcome back! It has been about 3 weeks since the beginning of the coding period, and I am making progress at a pace faster than I thought we could. Here are the details of the work I did in the first three weeks. 

My week prior to the beginning of the coding period was spent setting up a development environment on my computer, and learning about the internals of Scrapy. Since, Scrapy is python project, setting up an development environment is fairly straightforward.  Clone the Scrapy repository `git clone https://github.com/scrapy/scrapy`, and create a [virtual environment](https://realpython.com/python-virtual-environments-a-primer/) using `python3 -m venv venv` (it creates a Python 3 virtual environment on Ubuntu). Now, activate the environment using `source venv/bin/activate`. Install python dependencies by running `pip install -r requirements-py3.txt`. If you are planning to run tests locally, install test dependencies by running `pip install -r tests/requirements-py3.txt`. The setup is complete.

Scrapy uses [tox](https://tox.readthedocs.io/en/latest/) for testing. `tox` is virtual environment management tool that can be used to run tests using multiple versions of python. `tox` also reduces the work required for integrating CIs. To run tests using Python 2.7 and Python 3.7, use `tox -e py27 -e py37`. I had minor difficulty (I was unable to run `tox` using any version other than 2.7) as I was using `tox` for the first time, but I was easily able to solve it using online documentation and help from mentors. You can learn more about `tox` [here](https://medium.com/@alejandrodnm/testing-against-multiple-python-versions-with-tox-9c68799c7880).

First and second weeks were spend deciding on a interface specification, and implementing the interface on three existing `robots.txt` parsers. Using feedback from the mentors, I improved upon the specification I proposed in my GSoC proposal. Documenting the interface turned out to be harder than implementing it. Both [Sphinx](http://www.sphinx-doc.org/en/master/) and `reStructuredText` was new for me. I also found it difficult to occasionally describe things clearly (documentation is hard). While implementing the interface on top of `RobotFileParser`, I had to take deep dive into its source code. For some reason, I always had this belief that reading through the implementation of python (or any language) and its inbuilt modules, would be difficult and not really useful, and code would mostly be complex and cryptic. This doesn’t seem to be the case (at least with python). I should do more of this, looking at a module’s implementation for fun :smile:. I modified Scrapy to use the new interface instead of directly calling `RobotFileParser`.

Next, I will work on creating extra test environments in [Travis](https://travis-ci.org/) for testing third-party parser integration. I haven't work with [Travis](https://travis-ci.org/) or `tox` before. Also, I will document the functionalities provided by these parser in Scrapy documentation. I will also need to the make the code for testing integration more maintanble.

