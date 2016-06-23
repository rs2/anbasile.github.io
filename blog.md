---
layout: page
title: blog
permalink: /blog/
---


 <ul style="list-style-type:none">
 {% for post in site.posts %}
  <li class="postlist">
   <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
 {% endfor %}
 </ul>


