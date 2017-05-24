---
layout: post
title:  Menjalankan tg-cli di raspberry pi 3
date:   2017-4-16  17:44:00
excerpt: "Pengalaman menjalankan telegram cli di raspberry pi 3"
tags: [Raspberry Pi 3]
comments: true
---

Telegram, platform chat yang cukup populer. Ada yang menarik dari telegram ini, yaitu tersedia telegram cli (ce el i ya bukan coli) yang selanjutnya kita sebut tg-cli.

Nah, saya bermaksud membuat bot telegram menggunakan tg-cli yang akan run di raspi 3. So langkah pertama untuk keinginan saya tsb adalah bagaimana menjalankan tg-cli raspberry pi 3.

Sebenarnya, di laman repo tg-cli yaitu https://github.com/vysheng/tg.git sudah dijelaskan bagaimana cara untuk kompilasi tg-cli sesuai dengan OS yang kita gunakan. Tapi eh tapi tadi waktu saya praktekan, ada kendala error <code>Can not connect (tgl/mtproto-utils.c:101: BN2ull: Assertion `0' failed)</code>. Jadi saya tulis ulang aja disini beserta cara fix-nya.

<hr>
## You will need

**Working internet connection** :laughing:

## Check this out

1. of course <code>ssh</code> ke raspberry pi 3 kamu.
2. clone repo tg-cli ke raspberry pi 3.
```shell
git clone --recursive https://github.com/vysheng/tg.git
```
3. Pindah ke direktori hasil clone tadi
```shell
cd tg
```
4. Edit file <code>tg/tgl/mtproto-utils.c</code> untuk ngatasin error yang tadi saya sebutkan
```shell
nano tgl/mtproto-utils.c
```
Cari `assert (0); // As long as nobody ever uses this code, assume` yang berada pada **line 101 dan 115** , comment kedua baris tsb.

5. Pasang dependensi yang dibutuhkan
```shell
sudo apt-get install libreadline-dev libconfig-dev libssl-dev lua5.2 liblua5.2-dev libevent-dev libjansson-dev libpython-dev make
```
6. Jalankan perintah berikut ini:
```shell
./configure
make
```
7. Kalau sudah selesai, coba jalankan tg-cli
```shell
bin/telegram-cli -k tg/tg-server.pub -W
```
8. Masukan nomor HP dan tara....selesai. Tg-cli siap digunakan.

<hr>

Nah itu tadi tentang apa yang saya lakukan, jangan tanya kenapa kok gini kenapa kok gitu, ini maksudnya apa, dst. Karena saya tidak mudeng. wkwkwk
