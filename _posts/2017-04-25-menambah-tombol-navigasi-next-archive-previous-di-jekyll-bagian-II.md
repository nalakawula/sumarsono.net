---
layout: post
title: "Menambah Tombol Navigasi Next Archive Previous di Jekyll bagian II"
date: 2017-04-25 09:08:23
tags: [jekyll]
---
Pada artikel [sebelumnya]({{ site.baseurl }}{% post_url 2017-04-18-menambah-tombol-navigasi-next-archive-previous-di-jekyll %}), sudah ditulis caranya. Namun, saya kurang puas dengan hasilnya.

Nah, suatu ketika saya berkunjung ke blog teman, navigasinya bagus eui.. bentuknya tombol. Kemudian saya putuskan untuk meniru dari blog teman saya. Berikut ini source code nya:
{% raw %}
```html
<div class="page-navigation">
      <ul>
      {% if page.previous %}
        <li class="previous"><a href="{{page.previous.url}}" title="{{ page.previous.title }}">&larr; Previous</a></li>
      {% else %}
        <li class="previous disabled"><a>&larr; Previous</a></li>
      {% endif %}
        <li><a href="{{site.baseurl}}/archive/">Archive</a></li>
      {% if page.next %}
        <li class="next"><a href="{{page.next.url}}" title="{{ page.next.title }}">Next &rarr;</a></li>
      {% else %}
        <li class="next disabled"><a>Next &rarr;</a>
      {% endif %}
      </ul>
 </div>
```
{% endraw %}

nah berikut ini kode 'css' biar jadi cantik
{% raw %}
```css
.page-navigation {
    height:20px;
    margin:18px 0;
    display: block;
    text-align: center;
}
.page-navigation ul {
    padding:0;
    display: inline-block;
    margin:0;
    border:1px solid #ddd;
    border:1px solid rgba(0,0,0,0.15);
    border-radius:3px;
    box-shadow:0 1px 2px rgba(0,0,0,0.05);
    text-align: center;

}

.page-navigation li {
    display:inline
}
.page-navigation a {
    float:left;
    padding:0 14px;
    line-height:34px;
    border-right:1px solid;
    border-right-color:#ddd;
    border-right-color:rgba(0,0,0,.15)
}
.page-navigation a:hover {
    background-color:#eee
}
.page-navigation .disabled a,.page-navigation .disabled a:hover {
    background-color:transparent;
    color:#968896
}
.page-navigation .next a {
    border:0
}
```
{% endraw %}

Hasilnya, seperti yang anda lihat di bawah post ini. :+1:
<hr>
