---
layout: post
title: "memperbaiki tampilan emoji di gh-page"
date: 2017-04-17 15:52:42
---
Setelah berhasil memasang [jemoji](https://sumarouno.github.io/menambah-emoji-di-gh-page/){: target="_blank"} , ternyata ada kendala, tampilan emojinya terlalu **GEDE** <emoji>:laughing:</emoji>

Akhirnya saya tanyakan ke group pegelinux, disana dapat solasi <emoji>:laughing:</emoji>. Disarankan untuk mengatur ukurannya via css.

<hr>

Akhirnya saya tambahkan di file <code>css</code> :
{% highlight css %}
emoji {
    display: inline-block;
    height: 1em;
    width: auto;
}
{% endhighlight %}

contoh penggunaanya di post:
`<emoji>:+1:</emoji>` nanti jadi <emoji>:+1:</emoji>

dan tara...selesai, emoji tampil dengan normal, <emoji>:+1:</emoji>
