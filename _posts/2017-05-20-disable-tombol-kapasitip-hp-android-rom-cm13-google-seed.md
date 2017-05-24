---
layout: post
title: "Disable Tombol Kapasitip HP Android ROM CM13 Google Seed"
date: 2017-05-20 15:00:10
tags: [android]
---
Bosan menggunakan tombol fisik? ingin ganti ke softkey? sudah ganti tapi tombol fisik terasa *annoying*?

Mudah saja. Disable aja tombol kapasitipnya.
Caranya? check this out:
1. Hubungkan HP ke Laptop
2. Aktifkan `USB Debugging` di HP
3. Buka Termninal
4. Jalankan perintah adb shell dan minta hak ases `root`:
```shell
adb shell
su
```
5. Edit file `Generic.kl`:
```shell
vim /system/usr/keylayout/Generic.kl
```
6. Cari tulisan:
    - `key 139   MENU`
    - `key 172   HOME`
    - `key 158   BACK`

    Kemudian beri tanda `#` didepannya
7. Simpan
8. Exit adb shell
9. Reboot HP
```shell
adb reboot
```
