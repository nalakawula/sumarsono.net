---
layout: post
title: "memperbaiki tampilan emoji di gh-page"
date: 2017-04-17 15:52:42
tags: [jekyll]
---
Setelah berhasil memasang [jemoji]({{ site.baseurl }}{% post_url 2017-04-17-menambah-emoji-di-gh-page %}) , ternyata ada kendala, tampilan emojinya terlalu **GEDE** :laughing:

Akhirnya saya tanyakan ke group pegelinux, disana dapat solasi :laughing:. Disarankan untuk mengatur ukurannya via `css`.

Akhirnya saya tambahkan di file `css`:
```css
emoji {
    display: inline-block;
    height: 1em;
    width: auto;
}
```
contoh penggunaanya di post:
`:+1:` nanti jadi :+1:

dan tara...selesai, emoji tampil dengan normal, :+1:
