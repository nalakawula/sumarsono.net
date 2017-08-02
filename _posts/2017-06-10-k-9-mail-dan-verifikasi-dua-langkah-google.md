---
layout: post
title: K-9 Mail dan Verifikasi Dua Langkah Google
date: '2017-06-10 04:15'
tags:
  - android
---
Yesterday, saya merasa gerah dengan aplikasi Gmail untuk Android. Notifikasi email masuknya telat, menunggu aplikasinya dibuka dulu. Setelah saya telaah, ternyata aplikasi Gmail ini lumayan _rakus_ penggunaan RAM-nya, maklum HP saya HP _low end_ dengan spesifikasi rendah.

Oleh sebab itu, saya mencari aplikasi _email client_ yang ringan. Akhirnya ketemu dengan [K-9 Mail](https://play.google.com/store/apps/details?id=com.fsck.k9&hl=en). Ukurannya kecil.

Selesai unduh, langsung saya coba untuk masuk menggunakan akun Gmail saya, eh gak bisa login, dan tidak ada pesan error apapun. Setelah browsing, ternyata hal itu terjadi karena terkendala Verifikasi 2 langkah Google.

Nah, berikut ini langkah setup K-9 Mail untuk akun Google:
1. Kunjungi [Google Account settings page.](https://www.google.com/settings/account).
2. Klik __Sign-in & Security__
3. Di bagian __Password & sign-in method__, klik __App Passwords__
4. Di bawah tulisan __Select the app and device you want to generate the app password__, klik __Select App__ kemudian klik __other _(custom name)___
5. Masukan nama, misalnya _K-9 Mail Android_
6. Klik __GENERATE__ sehingga muncul _pop up_ __Generated app password__
7. Gunakanlah password yang muncul tersebut untuk login di Aplikasi K9-Mail.
8. Selesai

Semoga bermanfaat
