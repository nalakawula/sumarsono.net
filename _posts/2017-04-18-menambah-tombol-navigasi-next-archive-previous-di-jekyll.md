---
layout: post
title: "Menambah tombol navigasi next archive previous di jekyll"
date: 2017-04-18 08:03:23
tags: [jekyll]
---
Beberapa hari ini, saya mainan *static site* dengan memanfaatkan jekyll dan gh-page.

Nah hari ini, setelah saya lihat-lihat *static site* saya ada yang kurang. Dulu pas main wordpress ada yang namanya *next post* sama *previous post*.

Oleh karena itu, hari ini saya menambahkan fitur itu.

<hr>

## Check this out
1. edit <code>_layouts/post.html</code> . Tambahkan sebelum <code></article></code> biar lokasinya ada dibawah konten utama:
    {% raw %}
    ```html
    <div class="PageNavigation">
      {% if page.previous.url %}
      <a class="prev" href="{{page.previous.url}}"> « {{page.previous.title}}</a>
      {% endif %}

      {% if page.next.url %}
        <a class="next" href="{{page.next.url}}"> {{page.next.title}} »</a>
      {% endif %}
    </div>
    ```
    {% endraw %}

2. edit <code>css</code> . Tambahkan:
    {% raw %}
    ```css
     .PageNavigation {
      font-size: 16px;
      display: block;
      width: auto;
      overflow: hidden;
      }

    .PageNavigation a {
      display: block;
      width: 50%;
      float: left;
      margin: 1em 0;
      }

    .PageNavigation .next {
      text-align: right;
      }
    ```
    {% endraw %}

Selesai
<hr>
