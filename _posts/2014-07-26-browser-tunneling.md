---
published: true
layout: post
title: "Browser Tunneling"
author: Boy Sandy Gladies Arriezona
categories:
    - tools
tags:
    - tunnel
    - browser
comments: True
---

## Prolog

Okay, we will talk about tunneling. I have a task to do in a few days, I need to remote 3 servers which cannot be accessed from outside of my office. So, I guess I have to use a tunnel. With that being said, this is what I do to achieve that.

## Workaround

``` shell
$ ssh -D {port} -N {user}@{tunneled-ip-address} -p {tunneled-port}
```

Now, if I want to access some specific web page which can only be accessed from my office I only need to change how my browser connect to the internet. Let's say that the port I chose is 9999, in firefox I change my network configuration into this:
Firefox Configuration
