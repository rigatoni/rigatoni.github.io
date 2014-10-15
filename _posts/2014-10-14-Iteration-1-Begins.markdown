---
layout:     post
title:      Iteration 1 Begins
date:       2014-10-14
summary:    While the requirements and architecture documents still need to be cleaned up, coding is now officially underway.
---
We've made a few minor requirements changes and architecture tweaks since the last post. First is that we're going to begin with using RIT LDAP for user accounts, rather than Twitter. While Twitter will still be added in a later iteration, we realized that since not all users in a classroom will have a Twitter account, it's more important to start with something universal. In terms of architecture, we've decided to change the method of communication between Node and Python code. We decided that there were too many scalability risks with using TCP/IP, so instead we'll be communicating over HTTP, most likely using Tornado as a Python-based web server.

With those changes in mind, we've officially started our first two-week iteration. This means that on October 23rd, we'll be delivering a functional product, deployed to our VM, documented, and unit tested. With a shorter iteration schedule, the amount of functionality in each iteration will be smaller. For this iteration, we mostly will be doing initial structural setup of our application as well as getting the production server configured. On the Python side, we'll be adding support for tf-idf and removing capitalization and punctuation.