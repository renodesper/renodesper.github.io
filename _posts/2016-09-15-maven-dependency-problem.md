---
published: true
layout: post
title: "Maven Dependency Problem"
author: Boy Sandy Gladies Arriezona
categories: tools
tags:
    - maven
comments: True
---

I have a problem downloading several pom files from local artifactory. Well, those poms literally doesn't exist but the jar files are there, so it should not be a problem. The weird thing is it failed to build the package with maven.

So, I create those poms manually. And when I try to build it again:

``` shell
$  mvn package
```

The log said:

> [WARNING] The POM for "package" is invalid, transitive dependencies (if any) will not be available, enable debug logging for more details

Problem solved, continue to code.
