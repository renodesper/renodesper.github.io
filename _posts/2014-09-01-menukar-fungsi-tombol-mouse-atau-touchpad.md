---
published: true
layout: post
title: "Menukar Fungsi Tombol Mouse atau Touchpad"
author: Boy Sandy Gladies Arriezona
categories: linux
tags:
    - mouse
    - linux
comments: True
---

Mungkin ini terdengar aneh, tetapi saya mempunyai kebiasaan untuk menukar fungsi tombol yang ada di mouse walaupun sebetulnya saya bukan left-handed. Untuk menukar fungsi tombol yang ada di mouse kita bisa menggunakan perintah berikut:

``` shell
$ xmodmap -e "pointer = 3 2 1"
```

Ada masalah yang muncul jika kita menggunakan perintah di atas. Masalahnya adalah perintah tersebut akan menukar fungsi mouse secara umum, maksudnya adalah touchpad yang juga bisa digunakan selain mouse akan tertukar. Lalu bagaimana kita menyiasatinya? Kita bisa menggunakan fungsi *xinput*. Sebelumnya kita harus mencari tahu dulu id dari *touchpad* / *mouse* yang akan kita tukar fungsi tombolnya.

``` shell
$ xinput list
```

Fungsi di atas dapat digunakan untuk melihat id dari device-device yang kita gunakan. Cari id untuk *touchpad* / *mouse* kita lalu gunakan perintah berikut untuk menukar fungsi tombolnya:

``` shell
$ xinput set-button-map {id} 3 2 1
```
