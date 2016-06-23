---
layout: page
title: blog
permalink: /blog/
---
<div class="row">
 <ul style="list-style-tipe:none">
 {% for post in site.posts %}
  <li>
   <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
 {% endfor %}
 </ul>
</div>

