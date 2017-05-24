---
layout: post
title: "Membuat Tautan Referensi ke Artikel Lain dalam Jekyll"
date: 2017-05-24 11:20:47
tags: [jekyll]
---
Ketika kita menulis artikel untuk website, ada kalanya kita akan membuat referensi ke artikel lain yang pernah kita tulis. Jekyll pun bisa melakukan hal tersebut.

Nah, dulu saya menggunakan cara seperti ini:
{% raw %}
```
[artikel anu]({{ site.url }}/2017/04/18/anu-ini-inu-uni/
```
{% endraw %}

Menggunakan cara seperti itu, tentu saja bisa. Namun, akan ada kendala ketika kita mengubah `permalink` situs kita.

Bagaimana caranya agar referensi yang kita buat bisa otomatis mengikuti `permalink` situs kita? Ternyata jekyll memiliki fitur ini. Untuk keperluan seperti itu, gunakan cara seperti ini:

{% raw %}
```
[artikel anu]({{ site.baseurl }}{% post_url yyy-mm-dd-nama-artikel %})
```
{% endraw %}

Contoh:
{% raw %}
```
[artikel anu]({{ site.baseurl }}{% post_url 2017-04-18-anu-ini-inu-uni %})
```
{% endraw %}

Nantinya, kode `html` yang dihasilkan akan mengikuti `permalink` situs kita.


Sekian
