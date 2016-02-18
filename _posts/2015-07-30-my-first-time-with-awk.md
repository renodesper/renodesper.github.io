---
published: true
layout: post
title: "My First Time with Awk"
author: Boy Sandy Gladies Arriezona
tags:
    - awk
    - linux
comments: True
---

Tonight we'll talk about Awk. Actually, I've know it for a long time but I never had any chance to explore it. A few days ago, I need to remove some duplicate lines from a file BUT it should not be sorted. We can also use sort and uniq, but it will end up sorted before we got an actual result. I'm using this kind of script to remove it:

``` shell
$ awk '!x[$0]++' test_file.log > result_file.log
```

How is it? Interested to learn Awk even more?
