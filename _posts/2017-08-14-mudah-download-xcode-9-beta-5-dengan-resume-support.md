---
layout: post
title: Mudah Download Xcode 9 Beta 5 dengan Resume Support
date: '2017-08-14 13:22'
tags:
  - OSX

comments: true
---
Tiga hari ini, saya mencoba download Xcode 9 beta 5 yang berukuran segede gaban 0dan berkali kali menemui kegagagalan. Dan baru siang ini sukes. File berukuran 4.9GB ini akhirnya sukses masuk dalam penyimpanan pribadi saya.

Kendala yang saya temui adalah tidak bisa resume download yang terputus, berbagai download manager saya coba, seperti bawaan Safari, bawaan firefox, Downthemall, dan Folx. Semuanya tidak cocok dengan CDN `developer.apple.com` yang menggunakan auth berdasarkan cookie dari browser.

Jadi kita login ke `developer.apple.com`-->browser menyimpan cookie-->Download dimulai. Begitu cookie dalam browser expired, maka download tidak dapat dilanjutkan. Bagi saya yang kecepatan unduhan tidak secepat *the flash* benar-benar kerepotan.

Sampai akhirnya saya jengkel dan mencari solusi, baru siang ini secara tidak sengaja saya menemukan tulisan [Ian Dundas](http://iandundas.com/blog/2017/2/21/script-for-reliably-and-quickly-downloading-xcode-on-a-poor-connection). Beliau menulis script `ruby`untuk dowload xcode. **He is my lifesaver**. Thank you [Ian](http://iandundas.com/blog/2017/2/21/script-for-reliably-and-quickly-downloading-xcode-on-a-poor-connection).

Saya hanya perlu mengubah sedikit script-nya agar sesuai dengan keadaan saya, dan akhirnya xcode terdownload dengan selamat. Ringkasnya yang saya lakukan adalah sebagai berikut:
1. Pasang extensi [View Cookies](https://bitstorm.org/extensions/view-cookies/) untuk firefox.
2. Copy script [Ian Dundas](http://iandundas.com/blog/2017/2/21/script-for-reliably-and-quickly-downloading-xcode-on-a-poor-connection) simpan sebagi `download_xcode.rb`
3. Edit script tersebut
4. Buka firefox, kemudian buka https://developer.apple.com/download/
5. Login dengan akun apple id
6. Klik Download kemudian klik save File
7. Show all download pada firefox, kemudian pada proses download xcode, klik kanan, copy download link. Milik saya ini https://download.developer.apple.com/Developer_Tools/Xcode_9_beta_5/Xcode_9_beta_5.xip linknya.
7. Jalankan script `download_xcode.rb`
8. Akan diminta memasukan download link, paste link tadi.
9. kemudian akan diminta untuk memasukan cookie `ADCDownloadAuth`
10. Kembali ke halaman https://developer.apple.com/download/ kemudian tekan `cmd`+`i`, masuk ke tab Cookies
11. Cari cookie bernama `ADCDownloadAuth` dan copy `value`-nya
12. Selesai, download akan dimulai dengan resume support.
