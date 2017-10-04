---
layout: post
title: Share Koneksi Internet WIFI via Ethernet di Arch Linux
date: '2017-09-27 22:22'
tags:
  - arch linux
comments: true
---

Kamu ingin membagikan koneksi internet dari Wifi laptop ke LAN laptop?
Kamu pengguna distribusi Arch linux?
Kamu pengguna DE GNOME?

Jika iya, lanjutkan. Jika tidak? tetap lanjutkan.

### Topologi yang saya gunakan

Internet------(Wifi) laptop (LAN)------Raspberry Pi 3

### Step by step
1. Buka `nm-connection-editor`
2. Klik _Add_
3. Pilih _Ethernet_
4. Klik _Create…_
5. Klik _IPv4 Settings_
6. Pilih _Shared to other computers_ di menu Method
7. Masukan nama _share wifi ke lan_ dalam kolom isian connection name
8. Profit
