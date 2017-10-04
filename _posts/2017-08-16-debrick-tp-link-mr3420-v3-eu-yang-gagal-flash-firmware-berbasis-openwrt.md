---
layout: post
title: Debrick TP-LINK MR3420 V3 EU yang gagal Flash Firmware berbasis OpenWrt
date: '2017-08-16 07:14'
tags:
  - openwrt

comments: true
---
Setelah saya berhasil flash [pulpstone](http://pulpstone.pw), saya penasaran dengan firmware keluaran [ofmodemsandmen](https://ofmodemsandmen) yaitu `GoldenOrb`. Saya cek disana, ternyata ada untuk TP-LINK MR3420 V3, hanya saja tidak jelas bisa untuk versi EU atau tidak.

Modal nekat, coba flash pakai `mtd`, eh ternyata routernya K.O. Led indikator tidak menyala sama sekali.

Dengan harapan si router masih bernyawa, saya mencoba mengubungkan port wan ke laptop, menekan dan menahan tombol reset 5-10 detik, kemudian menekan tombol ON pada router, led indikator LAN di laptop berkedip, wah ada komunikasi. Akhirnya saya gunakan `wireshark` untuk menangkap informasi dari port lan.

Dari informasi yang ditangkap `wireshark` saya baca baris demi baris, ada informasi berikut ini:
1. Who has `192.168.0.66`? Tell `192.168.0.86`.
2. Read Request, File: `mr3420v3_tp_recovery.bin`, Tansfer type: octet, timeout=2. Dengan protokol `tftp`.

Wow, ternyata router saya masih hidup. Dari informasi diatas dapat disimpulkan sebagai berikut:
1. Router menggunakan IP 192.168.0.86 pada port wan.
2. Router mencari IP 192.168.0.66.
3. Router mencari file dengan nama `mr3420v3_tp_recovery.bin` yang akan diambil pakai protokol `tftp`

Dari situ, kita cukup turuti kemauan si router.
1. Set IP Address komputer kita menjadi 192.168.0.66
2. Siapkan `tftp server` pada komputer kita, terserah pakai program apa, sesuaikan dengan OS.
3. Download firmware original dari TP-Link dan rename menjadi `mr3420v3_tp_recovery.bin` kemudian taruh di direktori root tftp server.
4. Matikan router.
5. Tekan dan tahan tombol reset pada router.
6. Tekan tombol ON pada router.
7. Tunggu 5-10 detik kemudian lepaskan tombol reset.
8. Cek log tftp server, apakah ada komunikasi dari router, kalau ada, biarkan saja.
9. Tunggu 1-5 menit sampai router reboot otomatis.
10. Jreng jreng, router hidup lagi.
11. Login ke dashboard TP-Link dengan `user: admin` dan `pass: admin`
12. Selesai.
