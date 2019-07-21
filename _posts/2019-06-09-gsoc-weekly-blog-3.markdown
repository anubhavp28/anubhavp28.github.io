---
title: 'Protego parse!  :zap:'
layout: post
date: 2019-06-24 12:00
headerImage: false
tag:
- scrapy
- gsoc
category: blog
author: anubhavp
description: Weekly blogs for GSoC 2019
---

Hey! This is my third blog post for GSoC 2019, covering week 3 and 4.

The first part of my project concerning interface for `robots.txt` parsers is almost complete.
I have started working on a pure-Python `robots.txt` parser which I have named Protego. The name is borrowed from [Harry Potter](https://en.wikipedia.org/wiki/Harry_Potter_(film_series)) universe, where Protego is a charm that creates a shield to protect the caster. The end goal for Protego is to support all of the popular directives, wildcard matching, and a good number of less popular directives. Also, we aim to make Protego 100% compatible with [Google's robots.txt parser](https://github.com/google/robotstxt). We intend Protego to become the deafult `robots.txt` parser in Scrapy.

I have implemented support for all major directives in Protego. I have also implemented support for wildcard matching. I utilised pytest and tox to automate testing Protego on every version of Python. Furthur used Travis to run tests automatically on code push and pull requests. I borrowed tests from other parsers to check Protego on. Protego currently passes all tests borrowed from `reppy`, `rep-cpp` and `robotexlusionrulesparser`.
