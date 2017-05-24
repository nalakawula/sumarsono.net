---
layout: post
title: "Flash boot Android Menggunakan Fastboot"
date: 2017-05-20 15:56:26
tags: [android]
---
Melanjutkan artikel [membongkar boot.img]({{ site.baseurl }}{% post_url 2017-05-20-bongkar-boot.img-android-di-fedora-25 %})

Sekarang akan saya bahas cara flash file `new-boot.img` yang telah dibuat, metode yang saya pakai adalah menggunakan `fastboot` karena sangat mudah.

1. Aktifkan `usb debugging` di hp
2. Tancapkan ke laptop
3. Buka Terminal
4. `cd` ke lokasi new-boot.img
5. reboot HP ke mode `fastboot`
```
adb reboot-bootloader
```
6. Setelah muncul tulisan fastboot di layar HP, jalankan perintah ini:
```
fastboot flash boot new-boot.img
```
Hanya butuh beberapa detik untuk selesai
7. Reboot HP
```
fastboot reboot
```

Selamat, sekarang `/system` sudah termount dalam mode `rw`

:+1:
