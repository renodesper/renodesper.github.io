---
published: true
layout: post
title: "Editing Stream like Merlin The Mighty with Sed"
author: Boy Sandy Gladies Arriezona
tags:
    - sed
    - linux
comments: True
---

We already talk about Vim a couple of time. Let's move to sed. Sed is a stream editor (we already know that) that I used today. This is the case, I have some file (php file) which is badly written by someone (maybe for pissing me off) by changing some characters on it. Let's say they change *.php into *.rrrr* wherever possible. It's not a big deal if the file is only have a few lines, but imagine if it has 2000 lines and I should edit every *.rrrr* into *.php. Let's assume that I'm using a server, and even worse there many files that should be edited.

Enough with the long talk, this is how I roll:

``` shell
sed -i 's/\.rrrr/\.php/g' file.php
```

I also found an interesting sed & find combo, it looks like this:

``` shell
find folder_path -type f -exec sed -i 's/\.rrrr/\.php/g' {} \;
```

Neat, isn't it? :)
