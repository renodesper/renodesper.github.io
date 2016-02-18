---
published: true
layout: post
title: "Postgresql and Metasploit"
author: Boy Sandy Gladies Arriezona
categories: tools
tags:
    - postgresql
    - metasploit
comments: True
---

Dulu saya selalu penasaran bagaimana caranya menggunakan metasploit dan konfigurasi database-nya. Tetapi ternyata selama ini saya hanya kurang paham dengan alurnya. Berikut saya tuliskan apa yang sudah saya pahami saat ini.

## First Step

Hal pertama yang harus diperhatikan adalah database. Database yang digunakan oleh metasploit adalah postgresql. Setelah memasang postgresql di sistem yang kita miliki, kita harus membuat sebuah database yang nantinya akan digunakan oleh metasploit, begitu juga dengan user. Selain itu, hal penting lain yang harus diingat adalah port dimana database tersebut berjalan. Jika melihat di tutorial-tutorial yang sudah ada, maka port tersebut akan berbeda-beda. Oleh karena itu kita harus mencari tahu port yang digunakan oleh postgresql pada sistem yang kita miliki. Berikut contoh konfigurasi database yang saya gunakan.

``` yaml
production:
    adapter: postgresql
    database: database_msf
    username: user_msf
    password: password_msf
    host: 127.0.0.1
    port: 5432
    pool: 256
    timeout: 5
```

## Second Step (Final Step?)

Jika konfigurasi database sudah selesai dilakukan, maka selanjutnya kita cukup mengecek apakah metasploit sudah dapat mengakses database yang sudah kita sediakan.

``` shell
~ msfconsole
[-] Failed to connect to the database: could not connect to server: Connection refused
    Is the server running on host "127.0.0.1" and accepting
    TCP/IP connections on port 5432?

 ------------
< metasploit >
 ------------
       \   ,__,
        \  (oo)___
           (__)    )\
              ||--|| *


       =[ metasploit v4.9.3-dev [core:4.9 api:1.0]        ]
+ -- --=[ 1318 exploits - 716 auxiliary - 210 post        ]
+ -- --=[ 341 payloads - 35 encoders - 8 nops             ]
+ -- --=[ Free Metasploit Pro trial: http://r-7.co/trymsp ]

msf >
```

Seperti yang dapat kita lihat, metasploit masih belum dapat mengakses database yang kita buat. Ini disebabkan karena service postgresql belum kita nyalakan. Hal ini biasa terjadi jika kita memasang postgresql pada sistem yang kurang user friendly. Jangan dibandingkan dengan Kali yang sudah jelas-jelas menyediakan tools ini pada sistemnya.

Hal yang harus kita lakukan selanjutnya adalah menjalankan service postgresql dan mencoba menjalankan lagi metasploit.

``` shell
~ sudo systemctl start postgresql
~ msfconsole

       =[ metasploit v4.9.3-dev [core:4.9 api:1.0]        ]
+ -- --=[ 1318 exploits - 716 auxiliary - 210 post        ]
+ -- --=[ 341 payloads - 35 encoders - 8 nops             ]
+ -- --=[ Free Metasploit Pro trial: http://r-7.co/trymsp ]

msf > db_status
[*] postgresql connected to database_msf

msf >
```

Daaaaan, metasploit sudah dapat terkoneksi dengan database. Happy hacking… :)
