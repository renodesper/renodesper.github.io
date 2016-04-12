---
published: true
layout: post
title: "Set Default Browser"
author: Boy Sandy Gladies Arriezona
categories: linux
tags:
    - xdg
comments: True
---


For a few month after I did a fresh install of Archlinux, I found that when I try to click a link inside any application, it will call google chrome. So, I decide to fix it today. It actually easy. We can set our default browser with *xdg-mime* which is owned by *xdg-utils*.

## Requirement

- xdg-utils

## What I did

 We can set out default browser with these commands:

``` shell
$ xdg-mime default browser.desktop x-scheme-handler/http
```

And for https:
``` shell
$ xdg-mime default browser.desktop x-scheme-handler/https
```

