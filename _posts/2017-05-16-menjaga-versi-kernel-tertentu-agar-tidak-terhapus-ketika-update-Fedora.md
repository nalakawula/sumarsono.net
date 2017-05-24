---
layout: post
title: "Menjaga Versi Kernel Tertentu Supaya Tidak Terhapus Ketika Update Fedora"
date: 2017-05-16 12:21:04
tags: [fedora]
---

Secara default, Fedora 25 akan menjaga 3 versi kernel di mesin kita. Ketika ada pembaruan versi kernel, maka versi kernel terendah akan terhapus.

Ada kalanya karena suatu keperluan, kita perlu menjaga suatu versi kernel tertentu agar tidak terhapus ketika melakukan `dnf update`. Berikut ini caranya:
1. Kita list dulu daftar kernel yang terpasang di mesin kita, dari terminal kita jalankan:
```
rpm -qa kernel
```
Nah, nanti akan keluar daftar kernel yang terpasang, contohnya di saya:
```shell
kernel-4.10.14-200.fc25.x86_64
kernel-4.10.12-200.fc25.x86_64
kernel-4.10.13-200.fc25.x86_64
```
`-qa` == `-q` untuk `query` dan `-a` untuk `all` artinya query all kernel
2. Misalnya kita butuh `kernel-4.10.13-200.fc25.x86_64` agar tidak terhapus, jalankan perintah berikut:
```
sudo dnf mark install kernel-4.10.13-200.fc25.x86_64
```
apa itu `dnf mark`? berikut ini dari man page-nya:
```shell
dnf mark install <package-specs>...
    Marks the specified packages as installed by user. This can be useful if any package was installed as a dependency and is desired to
    stay  on  the  system when Auto Remove Command or Remove Command along with clean_requirements_on_remove configuration option set to
    True is executed.
```

Nah, sekian dulu.
