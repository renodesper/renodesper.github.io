---
published: true
layout: post
title: "Erasing Partition Table"
author: Boy Sandy Gladies Arriezona
categories: tools
tags:
    - partition
    - linux
comments: True
---

Well, I always use gparted to erase my partition table and sometimes it fail miserably. The most accurate way is to use sgdisk. We can erase our partition table like this:

``` shell
$ sgdisk --zap-all /dev/sda
```