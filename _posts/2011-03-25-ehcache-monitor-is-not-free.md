---
layout: post
title: Ehcache Monitor is not free
tags: [java]
---

We use Ehcache in a software project I am involved in. The open source Ehcache project is licensed under the Apache 2.0 License and can therefore be used without having to pay a license fee. I love it, I think it's GREAT.
<!--more-->

When I first tried Ehcache Monitor, I was happy to see that it solved a lot of our needs when it comes to monitoring and managing our caches across multiple servers in the cluster. However, it comes at a pretty high cost if you want to use it in a production environment. Terracotta do not currently sell it stand-alone, but only as a part of of the commercial versions of Ehcache (DX, EX or FX).

I currently have a dialogue going with a sales rep at Terracotta, and I hope they will start offering the monitor seperately, so that it can be used together with the open source version of Ehcache.
