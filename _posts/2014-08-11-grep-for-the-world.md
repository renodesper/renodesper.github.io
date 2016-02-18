---
published: true
layout: post
title: "Grep for The World"
author: Boy Sandy Gladies Arriezona
categories: tools
tags:
    - grep
    - linux
comments: True
---

Pernahkah kalian merasa kesulitan saat ingin mencari sebuah file yang kalian tidak tahu nama file-nya tetapi (sedikit) tahu apa isinya? Untuk mencari file yang misterius seperti ini kita bisa menggunakan grep. Berikut adalah contoh grep yang baru saja saya gunakan:

``` shell
$ grep -r -i "INSERT INTO news" *.py
```

Perintah di atas berguna untuk mencari file berakhiran ".py" yang di dalamnya mengandung kalimat "INSERT INTO news". Opsi "-r" akan membuat grep dapat mencari file tersebut secara rekursif pada folder tersebut. Opsi "-i" akan memberikan grep kemampuan untuk mencari teks secara "case insensitive".
