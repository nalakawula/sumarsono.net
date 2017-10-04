---
layout: post
title: Install Firmware berbasis OpenWrt di TP-Link MR3420 V3 EU
date: '2017-08-16 07:29'
tags:
  - openwrt

comments: true
---
Saya punya mainan baru, Wireless router merk TP-LINK. Tipe MR3420 v3 (EU version). Penasaran apakah router ini bisa di ganti firmware-nya ke firmware berbasis openwrt, akhirnya saya browsing. Dan ternyata bisa, walaupun belum official dan belum seramai seri pendahulunya, v1 dan v2.

Alkisah, saya berhasil memasang firmware dari [pulpstone](http://pulpstone.pw), dia berbasis openwrt dan yang membuat adalah orang Indonesia. Ikut bangga. Akan tetapi tidak semulus tutorial yang ditulis di [pulpstone](http://pulpstone.pw), karena punya saya versi EU, tidak bisa langsung flash dari menu `system upgrade` di dashboard TP-LINK.

Urutan keberhasilan saya adalah seperti ini:
1. Gunakan firmware `Tanaza EU version` dengan cara flash dari menu `system upgrade` di dashboard TP-LINK. `Tanaza` ini berbasis openwrt juga.
2. Upload firmware dari [pulpstone](http://pulpstone.pw) ke direktori `/tmp/` Tanaza.
3. Masuk ke sesi `ssh` Tanaza dengan `user: admin` dan `pass: tanaza`
4. Lakukan penulisan firmware pakai command `mtd`
5. Tunggu hingga selesai dan reboot otomatis.
6. Selesai. Silakan login ke pulpstone dengan `user: root` dan `pass: root`
