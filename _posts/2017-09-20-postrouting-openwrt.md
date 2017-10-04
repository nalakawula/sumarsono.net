---
layout: post
title: POSTROUTING Openwrt
date: '2017-09-20 09:46'
tags:
  - openwrt
comments: true
---
Melanjutkan [artikel tentang relayd]({{ site.baseurl }}{% post_url 2017-09-19-tp-link-mr3420-v3-eu-wds-mode-dengan-firmware-lede %})

Pada artikel tersebut, IP 192.168.2.0/24 yang tercantum dalam gambar topologi belum dapat terhubung ke internet. IP yang terhubung internet adalah 192.168.1.0/24.

Apakah bisa 192.168.2.0/24 dibuat terhubung internet? Bisa. Sederhana saja, kita tambah chain `POSTROUTING` pada tabel `NAT` yang akan melakukan `MASQUERADE` dari 192.168.2.0/24 ke interface `wlan0`.

```
iptables -t nat -A POSTROUTING -s 192.168.2.0/24 -o wlan0 -j MASQUERADE
```

Profit
