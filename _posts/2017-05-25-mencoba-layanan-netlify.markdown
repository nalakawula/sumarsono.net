---
layout: post
title: Mencoba Layanan Netlify
date: '2017-05-25 19:06'
tags:
  - jekyll
---
Tempat untuk _host_ static site ada banyak, termasuk _static site_ hasil dari `jekyll`. Yang sudah saya coba adalah:
1. __Github pages__, dulu saya gunakan untuk _hosting_ sumarouno.github.io dan sekarang saya pakai untuk _custom_ domain [sumarsono.id](www.sumarsono.id). Dapat `SSL` kalau tidak pakai custom domain, free `SSL` hilang kalau pakai custom domain. Makanya, saya pakai cloudflare agar jadi `https`.

2. __Google Firebase__, yang ini saya gunakan untuk _host_ [sumarsono.net](www.sumarsono.net) sebelum saya pindahkan. Enak sebenarnya, free `SSL` meskipun pakai custom domain. Tapi ini ribet kalau kita host kode sumber situs kita di github, butuh bantuan Travis CI agar bisa otomatis secara kontinyu, push (gh) --> build (Travis CI) --> deploy (Firebase). Alurnya terlalu panjang untuk sekedar _static site_.

Berangkat dari permasalahan diatas, saya mencoba _browsing_ mencari alternatif yang memenuhi syarat:
- __Terintegrasi dengan GitHub__, kode taruh di github, begitu ada _trigger_ otomatis melakukan _build_ tanpa kita setting pihak ke tiga seperti Travis CI.
- __Free SSL__, meskipun kita pakai custom domain dan tanpa kita ribet setting di pihak ke tiga seperti cloudflare.
- __Gratis__, ini syarat mutlak :laughing:

Akhirnya, saya mencoba [Netlify](https://www.netlify.com/), saya lihat dia memenuhi persyaratan, dan WAW praktis sekali dimata saya.
1. Sign up pakai GitHub
2. Klik tombol <kbd>New Site</kbd>
3. Klik tombol <kbd>GitHub</kbd>
4. Cari nama repo situs kita
5. Pilih `branch`
6. Isi `build command` (ada contohnya)
7. Isi `Publish directory` (ada contohnya)
8. Klik tombol <kbd>Deploy Site</kbd>
9. Bisa set custom domain
10. Dapat free ssl
11. Contohnya klik [disini](https://www.sumarsono.net/)

Untuk kategori _free plan_ ini sudah sangat cukup, keren. _Wanna try?__ go [here](https://app.netlify.com/)
