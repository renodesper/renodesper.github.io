---
published: true
layout: post
title: "Journey to Functional Programming"
author: Boy Sandy Gladies Arriezona
date: 2016-12-11 09:10:31 +0700
categories: haskell
tags:
    - haskell
    - functional programming
---

Dulu, dulu sekali. Saya pernah mencari tentang apa saja hal yang harus saya pelajari agar saya bisa lebih ahli dalam pemrograman Python. Lalu secara tidak sengaja saya menemukan jawaban di [stackoverflow](http://stackoverflow.com/posts/2576240/revisions) yang menyarankan untuk membaca buku [Real World Haskell](http://book.realworldhaskell.org/read/). Di sinilah perjalanan saya menuju Functional Programming dimulai. *And the journey begin~*



Saya sempat mempelajari Scala di tempat saya bekerja, hanya saja saat itu pekerjaan saya dipindahkan kembali ke pekerjaan yang menggunakan bahasa Python sehingga saya tidak terlalu dalam mempelajari Scala. Dan alasan kenapa saya memilih Haskell daripada Scala dalam mempelajari Functional Programming adalah karena saya sudah cukup lama mengenal Haskell. Saya katakan cukup lama karena antarmuka ([Xmonad](http://xmonad.org/)) di sistem operasi yang saya gunakan dibuat menggunakan Haskell. 



Pengalaman pertama saya saat melihat kode-kode Haskell adalah:

1. Wow!!

2. Cara bacanya bagaimana ya?

3. Karakter-karakter aneh apa itu dan apa maksudnya? (`.|.`, `!!`, `++`, `>>`, `$`, `::`, `-->`, `<+>`, `??`, `|||`, etc)

   ​

Saya yang terbiasa melihat kode-kode imperative dan OOP sangat pusing saat membaca kode Haskell. Bagaimana bisa sebuah bahasa pemrograman memiliki tingkat pemahaman yang cukup tinggi jika dibandingkan dengan bahasa yang pernah saya pelajari sebelumnya (C/C++, PHP, Python, Ruby, Go, Java, Javascript). Atau mungkin saya hanya belum pernah melihat orang-orang menggunakan karakter-karakter seperti di atas? *mungkin saja*



Untuk mempelajari Functional Programming saya harus mengubah cara pandang saya tentang bahasa pemrograman. Banyak sekali yang harus saya pelajari seperti apa itu *pure function*, *side effect*, *lazy evaluation*, dan hal-hal baru lainnya. Perjalanan saya masih panjang, semoga saja saya tidak akan menyerah di tengah jalan dan bisa memahami apa itu *Functional Programming*. 



Sebagai penutup, berikut akan saya sertakan kutipan kode haskell yang saya miliki:

``` haskell
myWorkspaces :: [String]
myWorkspaces = clickable . (map dzenEscape) $ [" Base ", " Code ", " Chat ", " Office ", " Graphic ", " Game ", " Other "]
    where clickable l = [ "^ca(1,xdotool key super+"
                        ++ show (n) ++ ")" ++ ws ++ "^ca()" |
                        (i,ws) <- zip [1..] l,
                        let n = i ]
```
