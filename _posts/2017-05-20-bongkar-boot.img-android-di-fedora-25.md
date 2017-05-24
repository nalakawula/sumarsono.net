---
layout: post
title: "Bongkar boot.img Android di Fedora 25"
date: 2017-05-20 15:16:24
tags: [android]
---
Hari ini saya mendapati custom ROM Android yang `/system` nya termount `ro` atau *read only*. Padahal saya mau edit file [ini]({{ site.baseurl }}{% post_url 2017-05-20-disable-tombol-kapasitip-hp-android-rom-cm13-google-seed %}) di `system`.

Usut punya usut, agar `/system` termount dalam mode `rw` harus bongkar `boot.img`. Untungnya sudah ada yang membuat `bash script` untuk *unpack* dan *repack* `boot.img`

1. Unduh [disini](https://github.com/GameTheory-/mktool.git) lalu ekstrak
2. Copy paste file boot.img ke dalam folder mktool
3. jalankan ./mktool
[![Fedora_winten]({{ site.baseurl }}/assets/img/ss-mktool.png)]({{ site.baseurl }}/img/ss-mktool.png)
4. Pilih **2** dan masukan nama file boot.img nya.
5. Edit file `/mktool/extracted/ramdisk/fstab.qcom`
6. Ubah baris:
```shell-script
/dev/block/bootdevice/by-name/system    /system     ext4    ro,barrier=1    wait
```
menjadi:
```shell-script
/dev/block/bootdevice/by-name/system    /system     ext4    rw,barrier=1    wait
```
7. Simpan
8. kembali ke jendela mktool, pilih repack. Nanti akan menghasilkan file `new-boot.img`
9. File tersebut siap di flash via fastboot flash

Selesai.
Next time, kita bahas cara flash file tadi pakai fastboot :+1:

Update: Sudah saya tulis cara flash-nya klik tombol `next` dibawah post ini :laughing:
