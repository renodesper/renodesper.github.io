---
published: true
layout: post
title: "Menghapus baris di Vim - 1"
author: Boy Sandy Gladies Arriezona
categories: tools
tags:
    - vim
    - linux
comments: True
---

## Case

Terkadang kita perlu menghapus beberapa baris secara berurutan dan secara spesifik. Contohnya adalah jika kita ingin menghapus 491 baris dari baris ke 105. Seperti yang kita tahu, kita bisa menggunakan dd untuk menghapus 1 baris di Vim. Tapi bagaimana untuk kasus di atas? Mengutip dari suatu blog, penggunaan Vim itu seperti kita berbahasa (thanks for Daniel Miessler for your awesome post). Caranya seperti berikut:

## Solution

    1. 491dd = menghapus 491 baris ke bawah dengan syarat posisi kita harus ada di baris 105
    2. d491j = menghapus 491 baris ke bawah dengan syarat posisi kita harus ada di baris 105 dan di posisi paling awal baris, kita juga bisa menghapus ke atas dengan cara mengganti j menjadi k
    3. :105,596d = menghapus 491 baris dari baris 105 sampai baris 596, kita harus tahu terlebih dahulu akhir baris yang kita inginkan dan harus berada di normal mode

Mudah kan? Saya juga baru saja mencoba menggunakannya. Just remember guys, practice makes expert.
