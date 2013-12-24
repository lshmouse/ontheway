---
layout: page
title: Welcome to lshmouse's blog
---
{% include JB/setup %}

## 联系方式    
    Email : lshmouse@gmail.com
    Sina weibo: @lshmouse

## 文章列表
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>



## 好文转载

如何写一篇好的技术博客 <http://elevencitys.com/?p=6152>

