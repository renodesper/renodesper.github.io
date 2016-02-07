---
published: true
layout: post
title: "Untracking The Tracked Ones"
tags:
    - git
    - linux
comments: True
---

Sudah beberapa hari saya mempunyai keinginan untuk memperbaiki projek yang saya lakukan. Secara tidak sengaja saya memasukkan virtual environment ke dalam repositori yang notabene seharusnya hanya diisi oleh projek yang saya kerjakan. Alhasil banyak sekali perubahan setiap saya mencoba mengerjakan kembali (bahkan) ketika saya tidak mengubah apapun.

Berikut cara yang saya temukan untuk meng-untrack file / folder yang sudah di-track:

``` shell
$ git rm --cached -r env
```

Setelah itu, folder tersebut bisa kita masukkan ke dalam file *.gitignore* seperti berikut:

``` shell
env/*
```
