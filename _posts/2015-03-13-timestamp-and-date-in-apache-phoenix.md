---
published: true
layout: post
title: "Timestamp and Date in Apache Phoenix"
author: Boy Sandy Gladies Arriezona
categories:
    - tools
tags:
    - timestamp
    - date
    - apache phoenix
comments: True
---

For a several days I've played with Apache Phoenix. Instead of playing with HBase directly, Phoenix helped me simplify HBase query (well, just a bit). What I want to tell you now is not about Phoenix in general but the difference between Timestamp and Date in Phoenix.

I have 2 column which have different format. I thought that both column should have different data type as well. Those format is like this:

    1. yyyy-MM-dd HH:mm:ss
    2. yyyy-MM-dd

When I use Date type for the 1st format, it doesn't show me the right result. It only shows me year, month, and day of the data like this: 2015-01-31. But in Timestamp, it shows me the right result. So, my assumption is I should be using Timestamp when I want to include the time (hour, minute, and second) of the data, and the rest should be use Date type.

Unfortunately, I found that my data in HBase is inconsistent. It has 7 hours difference with the actual data. The culprit is the difference of data type. The documentation says that I should include format type and timezone when I want to insert the date with Phoenix (in timestamp). So, instead of *to_date('2015-01-31 13:17:14')*, I should use *to_date('2015-01-31 13:17:14', 'yyyy-MM-dd HH:mm:ss', 'GMT+7')*. But that is a bit long and there is too many code to change, also I should remember which column have Timestamp and Date type.

At last, after hundreds thousand data insertion (wrong data of course), I found that I can also use Date type in every column as long as I explicitly write the format when I try to get the data with Phoenix.

That's all I wanna share, I hope it's useful.
