---
layout: post
title: "Mengganti Akes Github dari HTTPS ke SSH"
date: 2017-05-25 10:14:34
tags: [git]
---
Selama ini, aktivitas terkait `git` selalu saya lakukan _over_ `https`. Sampai akhirnya saya jenuh setiap kali harus menulis `username` dan `password`.

Kejenuhan nan mengikat itu yang membuat saya akhirnya berpaling dari `https` ke `ssh`. memindah akses via `https` ke `ssh` sangatlah mudah di git. Setelah kita selesai setup `key` di mesin kita dan di Github.com, langkah selanjutnya adalah mengubah `remote url` di mesin lokal.

Caranya:
1. Buka terminal.
2. Cek `remote url` yang sekarang:
```
git remote -v
```
Output jika masih pakai https:
```
origin	https://github.com/username/nama-repo.git (fetch)
origin	https://github.com/username/nama-repo.git (push)
```

3. Ubah ke `ssh` dengan menggunakan `remote set-url` :
```
git remote set-url origin git@github.com:username/nama-repo.git
```
output dari `git remote -v` nanti akan berubah menjadi:
```
origin	git@github.com:username/nama-repo.git (fetch)
origin	git@github.com:username/nama-repo.git (push)
```


Sekian
