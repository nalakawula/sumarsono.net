---
layout: post
title: Menambah 'Indonesia' di Setting Region & Language Arch Linux
date: '2017-05-29 09:34'
tags:
  - Arch Linux
---
Ketika saya melakukan pemasangan Arch Linux, `locale` yang saya gunakan dan saya _generate_ hanyalah `en_US.UTF-8 UTF-8`. Hal ini tentu saja akan menyebabkan isi dari setting `Region and Language` hanya ada `English` dan `US`.

Saya ingin, untuk bagian `format` menggunakan Indonesia, nah yang saya lakukan adalah berikut ini:
1. Buka file `/etc/locale.gen`
2. Cari baris `#id_ID.UTF-8 UTF-8` dan hapus tanda `#` -nya kemudian simpan
3. Selanjutnya jalankan `locale-gen`
```shell
sudo locale-gen
```
4. Buka setting `Region and Language`, sudah ada __Indonesia__ disana.

![Region and Language]({{ site.baseurl}}/assets/img/region-and-language.png)
