---
layout: post
title: >-
  Mengatasi Galat can't open device /dev/ttyACM0: Permission denied Ketika
  Upload Program ke Arduino dari Arch Linux
date: '2017-07-17 20:49'
tags:
  - Arduino
  - Arch Linux
---
Ceritanya, malam ini saya mendapat rongsokan `Arduino Mega 250` dari tukang rongsokan, secara _free_ alias gratis. Namanya barang gratis, kalau normal ya Alhamdulillah, kalau rusak ya sudah tidak mengapa.

Langsung ambil kabel USB dan tancap ke mesin Arch Linux. Si Arduino ini, sifatnya _masukan dan mainkan_ ketika dipasang di mesin berbasis GNU/Linux. Langsung terdeteksi sebagai:
```shell
Bus 006 Device 004: ID 2341:0042 Arduino SA Mega 2560 R3 (CDC ACM)
```

Dulu, ketika masih menggunakan Ubuntu, saya harus membuat `udev rule` untuk proses baca tulis ke Arduino. Bagaimana dengan Arch Linux? Saya coba langsung _fire in the hole_ saja pakai aplikasi `Arduino IDE`. Eh..muncul error:
```shell
can't open device "/dev/ttyACM0": Permission denied
```

Solusinya mudah saja, tinggal masukin aja user kita ke group `uucp`

```shell
sudo usermod -a -G uucp
```

Coba upload lagi programnya, dan tara...berhasil...


Terimakasih
