---
published: true
layout: post
title: "Starting Screen in Detach Mode"
author: Boy Sandy Gladies Arriezona
categories: tools
tags:
    - screen
    - linux
comments: True
---

For a few days I've been thinking about GNU/screen. I have some scripts that should be run inside screen everytime a reboot happened. I've been looking in stackoverflow, google, etc but haven't found anything useful. So I've been stuck with this kind of script: 

``` shell
$ screen -dmS screen_name some_command
```

It will create a new screen, run the command inside it and detach the screen. Well, it's pretty good actually. But, when the command is done (finished or killed) then the screen will be terminated. I won't know whether there is an error in my command or not. So, after a bit more googling I found about -X parameter and stuff. And now, my script looks like this:

``` shell
$ screen -dmS screen_name
$ screen -S screen_name -X stuff 'some_command\n'
```

the first line will create new screen and give it a name 'screen_name' the second line will send 'some_command\n' string to screen which similar with typing some_command and hitting enter

I can even send break (Ctrl-C) into screen with this: 

``` shell
$ screen -S screen_name -X stuff '^C'
```

With this, I can create a script that can modify whatever happen inside the screen. I can combine it with fabric if I want.
