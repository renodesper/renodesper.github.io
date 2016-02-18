---
published: true
layout: post
title: "LiveReload Integration"
author: Boy Sandy Gladies Arriezona
categories:
    - tools
tags:
    - livereload
    - web development
    - python
comments: True
---

## Introduction

Apa itu livereload? LiveReload adalah sebuah tool yang dapat kita gunakan untuk melakukan reload (refresh) pada browser sesuai dengan trigger tertentu. Misalnya jika sebuah file disimpan, jika ada sebuah GET request, bahkan kita juga bisa menambahkan delay sebelum reload dijalankan. Lalu hal apa saja yang harus kita lakukan untuk dapat menggunakan livereload?
Sublime Text and LiveReload Integration

Oke, ada 2 pilihan server yang bisa kita (saya sudah coba) gunakan. Yang pertama adalah plugin livereload yang sudah terintegrasi dengan sublime text. Dengan plugin ini, kita bisa menjalankan dan mematikan livereload langsung dari sublime text dan livereload langsung aktif begitu sublime text dinyalakan. Plugin ini bisa didownload di LiveReload.

## Any Text Editor and LiveReload Integration

Pilihan selanjutnya yang dapat kita gunakan adalah python-livereload. Jika kita memilih untuk menggunakan python-livereload maka kita dapat menggunakan text editor apapun, contohnya kita bisa menggunakan Vim. Yang perlu kita lakukan hanyalah menjalankan livereload dengan menyertakan directory dimana file-file yang digunakan berada. Berikut adalah isi help dari python-livereload:

``` shell
usage: livereload [-h] [-p PORT] [directory]

Start a `livereload` server

positional arguments:
  directory             Directory to watch for changes

optional arguments:
  -h, --help            show this help message and exit
  -p PORT, --port PORT  Port to run `livereload` server on
```
