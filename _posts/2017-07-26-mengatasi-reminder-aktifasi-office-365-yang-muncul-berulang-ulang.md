---
layout: post
title: Mengatasi Reminder Aktifasi Office 365 yang Muncul Berulang-ulang
date: '2017-07-26 11:14'
tags:
  - Windows
---
![Reminder Office 365]({{ site.baseurl }}/assets/img/365.PNG)

Kemarin, dapat Lenovo AIO PC yang mana sudah terpasang Windows 10 Home. Umumnya *unboxing*, buka kardus dan tes Power ON. Begitu hidup, akan diarahkan untuk *setup* akun Window dan Lenovo ID.

Terlalu panjang *Skip Skip*...................

Singkat cerita, ada office 365 didalamnya, saya buang dan ganti Office 2016. Setelah Windows dan Office saya aktifkan via internet, eh ada yang ngeselin. Setiap buka aplikasi Office, selalu muncul peringatan untuk aktifasi Office 365. Sungguh *shitty shit* dan *annoying*. Di restart masih sama saja.

Coba *browsing*, dengan kata kunci "annoying office 365 activation reminder" dan ternyata ada yang mengalami hal yang sama, dan sudah ada solusinya. Berikut saya kutip dari [sini](https://support.microsoft.com/en-us/help/3170450/repeated-activation-prompts-occur-after-installing-volume-license-vers)

To resolve this problem, export the following registry keys and delete from computer.

1. Close activation screen.
2. On the Start menu, click Run.
3. Type regedit, and then press Enter.
4. Select the following key in the registry.
```
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\16.0\Common\OEM
```
5. Right click the OEM value and click File>Export.
6. Save the key
7. Once the key is backed-up, click on Edit>Delete
8. Repeat steps 4-7 with following key
```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\16.0\Common\OEM
```
9. Exit Registry Editor

restart dan selesai.

Semoga bermanfaat.
