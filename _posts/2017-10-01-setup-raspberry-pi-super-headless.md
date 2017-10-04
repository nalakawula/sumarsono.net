---
title: Setup Raspberry Pi Super Headless
date: '2017-10-01 18:50:58'
tags: raspberry pi
comments: true
layout: post
---

Kok super headless?
Kasusnya begini, kita punya:
1. Raspberry Pi 3
2. Kabel LAN
3. Flashdisk Sandisk 4GB
4. Adaptor 5V3A
5. Laptop
6. USB TTL

Saya sebut super headless karena raspi akan saya setup tanpa DHCP server.

### Langkah-langkahnya
1. Download OS untuk raspberry pi, Raspbian Lite  [DISINI](https://www.raspberrypi.org/downloads/raspbian/).
2. Restore image raspbian ke flashdisk, terserah mau pakai tool apa, `dd`, `gnome-disk`, `etcher`.
3. Setelah selesai, akan muncul partisi `boot` dari flashdisk, buka saja.
4. Enable UART raspi, Cari file `config.txt` kemudian tambahkan `enable_uart=1`
5. Pasang flashdisk ke raspi
6. Hubungkan USB TTL ke raspi dan laptop
* 			GND --- GND
* 			RX --- TX
* 			TX --- RX

7. Di laptop pasang aplikasi buat UART, misalnya `screen`, `putty`.
8. Akses UART, `sudo screen /dev/ttyUSB0 115200`
9. Hidupkan raspi, nanti muncul log boot kemudian muncul login prompt.
10. Profit

Kalian pasti menyadari kalau saya tidak memakai microSD, perlu kalian ketahui bahwa raspi 3 bisa boot dari USB.