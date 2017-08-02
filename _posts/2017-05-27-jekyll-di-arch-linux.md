---
layout: post
title: Jekyll di Arch Linux
date: '2017-05-27 10:51'
tags:
  - jekyll
---
- Kamis, 25 Mei 2017 saya melakukan pemasangan Arch Linux untuk menggantikan Fedora 25.
- Jumat, 26 Mei 2017, Arch Linux di mesin saya, sudah siap digunakan.
- Sabtu, 27 Mei 2017, Saya ingin melanjutkan penulisan artikel untuk [sumarsono.id](https://www.sumarsono.id)

[sumarsono.id](https://www.sumarsono.id) ini dibangun menggunakan Jekyll, maka saya perlu setup jekyll untuk mesin Arch Linux saya. Berikut ini, langkah-langkahnya:
1. Install `ruby` karena kita butuh `RubyGems`:
```shell
sudo pacman -S ruby
```

2. Selanjutnya edit `.bashrc` dan tambahkan:
```shell-script
PATH="$(ruby -e 'print Gem.user_dir')/bin:$PATH"
```
3. restart terminal
4. Update paket `gem`:
```shell
gem update
```
5. Install `bundler` dan `jekyll`
```shell
gem install jekyll bundler
```
6. Masuk ke direktori _static site_ milik kita dan install paket yang diperlukan:
```shell
bundle install
```
6. Setelah selesai, coba run _static site_ kita secara lokal
```shell
bundle exec jekyll serve
```

Kalau berhasil run, berarti sudah beres. :+1:
