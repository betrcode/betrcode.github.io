---
layout: post
title: "Cheap Oracle virtualization"
tags: [oracle]
---

## Summary
Use multiple Oracle instances in the same machine instead of multiple virtualized hosts in the same machine.
<!--more-->

![Illustration of virtualization](/images/oracle-db-instances-279x300.png)

## Intro
I read [an article in Computer Sweden today where Kappahl couldn't do virtualization of their Oracle databases](http://computersweden.idg.se/2.2683/1.392449/kappahl-har-trottnat-pa-oracle) (article in swedish) because of expensive licence costs. In this article, I would like to offer a simple and cheap option to Oracle virtualization.

## Why virtualization?
Organizations want to virtualize their Oracle databases for many reasons, one being to reduce license costs. Other reasons include reducing hardware costs and making it easy to add new databases.

Simply put, hardware virtualization is basically about exchanging many physical servers for a single big server.

![Many small to one big](/images/virtualization-212x300.png)

You may prefer [the wikipedia definition of virtualization](https://en.wikipedia.org/wiki/Virtualization), but mine is short, sweet and simple.

## The alternative solution
Instead of doing Oracle virtualization using VMWare or Oracle VM, you can install several Oracle instances in a single Oracle installation, in a single machine. This is not what people usually mean when they say virtualization, but you get many of the benefits this way, and it will reduce your Oracle license costs!

### Pros
* Still easy to start/stop individual instances
* Still easy to add/remove individual instances
* Still easy to configure memory and disk usage per instance
* No need to learn/buy any virtualization technique

### Cons
* All instances will run on the same Oracle binaries, meaning all will run on the same Oracle version (some may consider this a benefit, when you've reached it...)
* All Oracle instances will run on the same OS.

## Real world experience
I have seen this work very well, especially for testing and development installations. Virtualization of databases in a production environment may not be as common, but there's no reason it shouldn't work there aswell.
