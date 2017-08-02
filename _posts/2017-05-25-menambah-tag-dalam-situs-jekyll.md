---
layout: post
title: "Menambah Tag dalam Situs Jekyll"
date: 2017-05-25 09:10:39
tags: [jekyll]
---

Kemarin pagi, dihari yang cerah nan hangat, terlintas dalam pikiran saya [sumarsono.id](https://www.sumarsono.id) kalau diberi _tagging_ sepertinya keren.

Siangnya, di hari nan panas saya mencari referensi dan menemukan situs yang mengerti apa yang ada dalam benak saya kala itu, yakni situsnya [charli](http://charliepark.org/tags-in-jekyll/) dan situsnya [Pavel D](http://pavdmyt.com/how-to-implement-tags-at-jekyll-website/). Awesome.

Di malam nan dingin merasuk sukma, saya mewujudkan angan. Dari dua referensi, saya menerapkan _tagging_ yang ditulis [Pavel D](http://pavdmyt.com/how-to-implement-tags-at-jekyll-website/) dengan sedikit modifkasi agar pas dengan [sumarsono.id](https://www.sumarsono.id). Berikut ini rangkumannya:

1.Beri `tags` pada setiap `front matter` masing-masing artikel yang kita tulis. Contohnya:

{% raw %}
```
---
layout: post
title: "Menambah Tag dalam Situs Jekyll"
date: 2017-05-25 09:10:39
tags: [jekyll]
---
```
{% endraw%}

2.edit `_layout/post.html`, tambahkan:

{% raw %}
```html
<ul class="tags">
    {% for tag in page.tags %}
      <li><a href="/tags#{{ tag }}" class="tag">{{ tag }}</a></li>
    {% endfor %}
</ul>
```
{% endraw %}

Tujuannya agar setiap artikel muncul `tag` -nya (lihat artikel ini, dibawah Judul ada tanggal dan tag).

3.Nah sekarang, tinggal membuat `page` yang isinya kumpulan semua `tag`. Buatlah file dengan nama `tags.md` di folder root site kita,kemudian isi dengan:
{% raw %}
```html
---
layout: page
title: Tags
permalink: /tags/
---
<!-- Get the tag name for every tag on the site and set them
to the `site_tags` variable. -->
{% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}

<!-- `tag_words` is a sorted array of the tag names. -->
{% assign tag_words = site_tags | split:',' | sort %}

<!-- List of all tags -->
<ul class="tags">
  {% for item in (0..site.tags.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ tag_words[item] }}{% endcapture %}
    <li>
      <a href="#{{ this_word | cgi_escape }}" class="tag">{{ this_word }}
        <span>({{ site.tags[this_word].size }})</span>
      </a>
    </li>
  {% endunless %}{% endfor %}
</ul>
---


<!-- Posts by Tag -->
<div>
  {% for item in (0..site.tags.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ tag_words[item] }}{% endcapture %}
    <h2 id="{{ this_word | cgi_escape }}">{{ this_word }}</h2>
    {% for post in site.tags[this_word] %}{% if post.title != null %}
      <div>
        <span style="float: left;">
          <a href="{{ post.url }}">{{ post.title }}</a>
        </span>
        <span style="float: right;">
          {{ post.date | date_to_string }}
        </span>
      </div>
      <div style="clear: both;"></div>
    {% endif %}{% endfor %}

  {% endunless %}{% endfor %}

</div>
```
{% endraw %}

4.Waktunya memberi style, edit `main.css`, tambahkan:
```css
.tags {
  list-style: none;
  margin: 0;
  overflow: hidden;
  padding: 0;
  background: #fdf6e3;
  color: #2a7ae2
}

.tags li {
  float: left;
}

.tag {
  background: #eee;
  border-radius: 3px 0 0 3px;
  color: #999;
  display: inline-block;
  height: 26px;
  line-height: 26px;
  padding: 0 20px 0 23px;
  position: relative;
  margin: 0 10px 10px 0;
  text-decoration: none;
  -webkit-transition: color 0.2s;
}

.tag::before {
  background: #fff;
  border-radius: 10px;
  box-shadow: inset 0 1px rgba(0, 0, 0, 0.25);
  content: '';
  height: 6px;
  left: 10px;
  position: absolute;
  width: 6px;
  top: 10px;
}

.tag::after {
  background: #fdf6e3;
  border-bottom: 13px solid transparent;
  border-left: 10px solid #eee;
  border-top: 13px solid transparent;
  content: '';
  position: absolute;
  right: 0;
  top: 0;
}

.tag:hover {
  background-color: crimson;
  color: white;
  text-decoration: none;
}

.tag:hover::after {
   border-left-color: crimson;
}
```

Hasilnya poin 3 dapat dilihat [disini]({{ site.url }}/tags)

Sudah selesai, any suggestion? feel free to [contact]({{ site.url }}/contact) me.
Thanks
