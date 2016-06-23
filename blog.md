---
layout: page
title: blog
permalink: /blog/
---
<div class="row" style="font-size:1.3em">
 <ul style="list-style-type:none">
 {% for post in site.posts %}
  <li style="before:{content: '>>';padding-right: 8px;"}>
   <a href="{{ post.url }}">{{ post.title }}</a>
  </li>
 {% endfor %}
 </ul>
</div>

