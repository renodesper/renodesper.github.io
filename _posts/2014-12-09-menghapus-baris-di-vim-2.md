---
published: true
layout: post
title: "Menghapus baris di Vim - 2"
author: Boy Sandy Gladies Arriezona
tags:
    - vim
    - linux
comments: True
---

## Case

Terkadang kita ingin menghapus baris-baris tertentu yang hanya mengandung kata-kata yang spesifik. Contohnya jika ingin menghapus log tetapi menyisakan baris yang mengandung kata **warning** atau **error** atau lainnya.

## Solution

Ada 2 ex command yang dapat kita gunakan yang berhubungan dengan masalah tersebut. 

	1. :g/{pola yang ingin dicari}/{perintah yang ingin dijalankan setelah pola ditemukan}
	2. :v/{pola yang tidak ingin dicari}/{perintah yang ingin dijalankan setelah pola ditemukan}

## Example

    1. Untuk menghapus setiap baris yang mengandung pola "warning" kita bisa menggunakan:
       :g/warning/d

    2. Untuk menghapus setiap baris yang tidak mengandung pola "warning" kita bisa menggunakan:
       - :v/warning/d
       - :g!/warning/d

Jika ingin mencoba perintah-perintah tersebut saya sarankan untuk menggunakan 1 file yang memiliki banyak kata dan kalimat, contohnya saya menggunakan 1 story yang saya ambil dari booktrust.

*PS: Pola yang dicari bisa juga menggunakan regex*
