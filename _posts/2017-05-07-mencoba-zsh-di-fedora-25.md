---
layout: post
title: "Mencoba ZSH di Fedora 25"
date: 2017-05-07 19:12:25
---

Berawal dari perbincangan di group telegram, Saya jadi ingin mencoba (lagi) `ZSH` untuk menggantikan `BASH`. Salah satu yang saya suka dari ZSH adalah tampilannya yang menarik, ditambah lagi dengan adanya `Oh My Zsh`.

Mengganti BASH dengan ZSH di Fedora 25 terbilang cukup mudah, berikut ini caranya:
1. Install paket `zsh` dan `util-linux-user`. Dari `util-linux-user` kita butuh `chsh` untuk me-replace bash dengan zsh.
```
sudo dnf install zsh util-linux-user
```
2. Ganti bash menjadi zsh dengan cara:
```
chsh -s /usr/bin/zsh
```
3. Tutup terminal dan buka lagi, `bash` sudah tergantikan oleh `zsh`

Nah, next time kita bahas `oh my zsh`.