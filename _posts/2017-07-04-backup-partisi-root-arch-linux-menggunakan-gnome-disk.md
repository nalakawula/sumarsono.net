---
layout: post
title: Backup Partisi Root Arch Linux Menggunakan Gnome Disk
date: '2017-07-04 08:57'
tags:
  - arch linux
---
Saya berniat memindahkan sistem operasi Arch Linux yang saya gunakan ke SSD lain, sehingga saya tidak perlu *setup* arch linux dari awal. *setup* arch linux dari awal itu sangat *wasting time* dan boros kuota. Alih alih mau produktif malah jadi kontra produktif.

Kronologi:
1. Backup partisi Root
2. Simpan ke HDD eksternal
3. Pasang SSD baru
4. Restore partisi Root
5. Install dan konfigurasi grub

Oleh sebab itu, kenapa tidak *clone* aja systemnya, begitu di *restore* sudah tidak ribet *setup* ini itu.
Dari banyak referensi *clone*, saya memilih menggunakan `dd` karena built in dalam sistem operasi GNU/Linux secara umum. Ditambah lagi, DE Gnome-shell yang saya gunakan sudah ada *frontend* untuk `dd` yakni `gnome-disk`. Tentu saja enak dan mempercepat proses, tinggal klik klik tunggu dan selesai.

Nah, untuk menghindari galat yang tidak saya inginkan, maka saya melakukan *clone* dari *live system* GNU/Linux. Berikut ini prosesnya:
1. Boot dari live systemnya
2. Buka gnome-disk
![Gnome Disk]({{ site.baseurl }}/assets/img/gnome-disk-c.jpeg)

Nah langkah selanjutnya:
1. Klik Disk yang mau di backup partisinya
2. Klik Partisi yang mau di Backup
3. Klik ikon gear
4. Klik create partition image
5. Kemudian tentukan lokasi penyimpanan dan beri nama filenya.
6. Selesai.

Untuk proses *restore* akan saya tulis dalam artikel lain.

Terimakasih
