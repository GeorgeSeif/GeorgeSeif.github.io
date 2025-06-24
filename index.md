---
layout: home
title: Home
sidebar: false
---

- [About](/about/)
- [Quotes](/quotes/)
- [Blog](/posts/)


Welcome!

I’m George, and this is my website.


### Latest Posts

{% for post in site.posts limit:5 %}
- [{{ post.title }}]({{ post.url | relative_url }})  
  <small>{{ post.date | date: "%b %-d, %Y" }}</small>
{% endfor %}

