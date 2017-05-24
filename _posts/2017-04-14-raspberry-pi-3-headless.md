---
layout: post
title:  Raspberry pi 3 Headless Mode
date:   2017-4-14  21:21:00
excerpt: "Pengalaman menjalankan raspberry pi 3 headless mode"
tags: [Raspberry Pi 3]
comments: true
---

Yo...bicara soal raspi 3 lagi. Dalam menggunakan raspi 3 mestinya membutuhkan perangkat tambahan untuk konfigurasi, minimal keyboard dan monitor.
Bagaimana kalau kita tidak punya keduanya? pusing. Haha. Tenang, akan saya tulis bagaimana mengkonfigurasi raspi 3 meskipun tidak punya monitor sama keyboard untuk dipasang di raspi 3.

<hr>

Nah, pada artikel ini akan saya share:
1. Install Raspbian Lite.
2. Mengakses raspi 3 meskipun tidak punya monitor dan keyboard untuk raspi.

Apa yang dibutuhkan:
1. Raspberry pi 3
2. Microsd
3. Laptop/komputer
4. Card reader
5. Kabel LAN



<hr>

## Here, what i did

1. Download image raspbian **lite**
2. Pasang microsd ke card reader.
3. Pasang card reader ke laptop.
4. <code>dd</code> image raspbian lite ke microsd, kalau pakai ms windows gunakan aplikasi win32 disk imager.
Contohnya:
```shell
sudo dd if=/lokasi/image/raspbian.img of=/lokasi/microsd/sdx bs=4MB && sync
```
5. Tunggu proses dd sampai selesai
6. Kalau sudah selesai _eject_ lalu pasang ke laptop lagi.
7. Enable <code>ssh</code>, caranya:
- masuk ke folder `boot`
- buat file dengan nama `ssh` (tanpa ekstensi, tanpa isi)

8. Kalau sudah selesai _eject_ lalu pasang ke raspberry pi 3 dan hidupkan raspi 3 nya.
9. Sembari menunggu raspi3 untuk boot, siapkan beberapa hal berikut:
- Aktifkan dhcp server untuk port lan di laptop, terserah mau pakai cara apa. misalnya pakai metode share koneksi wlan ke ethernet.
- pasang kabel lan di raspi dan di laptop.

10. Scan IP address milik raspberry pi 3, ini dilakukan karena IP address yg diperoleh raspi itu random dari dhcp. Di gnu/linux, saya pakai nmap. Kalau di ms windows pakai angry ip scanner. Contohnya:
```shell
sudo nmap -sP 10.42.1.0/24
```
`10.42.1.0/24` dapat darimana? dari <code>ifconfig</code> . Nah nanti muncul begini:
```shell
Starting Nmap 7.40 ( https://nmap.org ) at 2017-04-16 11:51 WIB
Nmap scan report for 10.42.1.10
Host is up (0.00032s latency).
MAC Address: xx:xx:xx:xx:xx:xx (Raspberry Pi Foundation)
Nmap scan report for 10.42.1.53
Host is up (0.00022s latency).
```

11. Setelah diperoleh IP address milik raspi misalnya 10.42.1.53, lakukan ssh ke raspi 3, dengan `user: pi` dan `pass: raspberry` Kalau di windows bisa menggunakan putty atau bitvise ssh client.
Contohnya:
```shell
ssh pi@10.42.1.53
```
11. Selesai

Nah itu tadi tentang apa yang saya lakukan untuk mengakses raspberry pi 3 dari laptop.
