---
published: true
layout: post
title: "New VPS for Node"
author: Boy Sandy Gladies Arriezona
categories:
    - linux
tags:
    - vps
    - node
    - npm
    - centos
comments: True
---

Kita skip dulu bahasan tentang Vim yang ada di post sebelumnya. Kemarin saya baru saja menyewa sebuah vps yang nantinya akan saya gunakan untuk riset. VPS tersebut saya pasangkan Centos 7 x86_64. Hal pertama yang saya lakukan adalah memasang nodejs dan npm. Berikut langkah - langkah yang saya lakukan.

## Update sistem

``` shell
$ yum update
```

## Instal EPEL (Extra Packages for Enterprise Linux) Repository

``` shell
$ yum install epel-release
```

## Instal Node.js dan npm

``` shell
$ yum install nodejs
$ yum install npm
```

Dokumentasi di situs Ghost mengatakan bahwa versi Node.js dan npm yang direkomendasikan adalah versi 0.10.30 untuk Node.js dan 1.4.21 untuk npm. Oleh karena itu pastikan agar Node.js dan npm yang kita instal sudah sesuai.
