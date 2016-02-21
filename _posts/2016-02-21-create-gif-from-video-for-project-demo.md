---
published: true
layout: post
title: "Create Gif from Video as Project Demo"
author: Boy Sandy Gladies Arriezona
categories: linux tools
tags:
    - ffmpeg
    - simple screen recorder
comments: True
---


This time I will show you how to make a gif from a video. Why do we need this? Well, a few hours ago I need to create a demo of a program to get a job. But I can't give them the source code, that's why I just show them how the program works.

## Requirement

- Simple Screen Recorder / similar software
- ffmpeg

## What I did

The first thing we need to do is create a video with Simple Screen Recorder / similar software. I make an avi video, but I guess it will work for any kind (but maybe not all kind) of video format. If we use Simple Screen Recorder, we need to specify video input, output format, output location, and frame rate.

The next step is to use ffmpeg to create gif file. Let's assume that the video is rec.avi and we want to create rec.gif, also we want the gif width to be 800px with the appropriate height. Do not forget to specify the frame rate, this time we will use 15 fps. This is the command I use to create the gif:

``` shell
ffmpeg -i rec.avi -r 15 -vf scale=800:-1 rec.gif
```

Now, we can send that gif to show them the demo.
