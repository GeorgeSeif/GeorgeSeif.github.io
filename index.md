---
layout: home
title: Home
sidebar: false   # full‐width intro
---

<!-- 1. In-page navigation links (if you want extra ones beyond your header) -->
<nav class="hero-nav">
  <a href="{{ '/about/' | relative_url }}">About</a>
  ·
  <a href="{{ '/quotes/' | relative_url }}">Quotes</a>
  <!-- future: · <a href="{{ '/blog/' | relative_url }}">Blog</a> -->
</nav>

<!-- 2. Hero welcome blurb -->
<section class="hero-intro">
  
  ## Welcome!  

  I’m George, and this is my website.  

</section>

<!-- 3. Recent posts loop -->
<section class="recent-posts">

  ### Latest Posts

  <ul class="post-list">
    {% for post in site.posts limit:5 %}
      <li>
        <a href="{{ post.url | relative_url }}">
          {{ post.title }}
        </a>
        <small>{{ post.date | date: "%b %-d, %Y" }}</small>
      </li>
    {% endfor %}
  </ul>

  {% if paginator.total_pages > 1 %}
    <nav class="pagination">
      {% if paginator.previous_page %}
        <a href="{{ paginator.previous_page_path | relative_url }}">&laquo; Prev</a>
      {% endif %}
      {% for page in (1..paginator.total_pages) %}
        {% if page == paginator.page %}
          <span class="page-number current">{{ page }}</span>
        {% else %}
          <a class="page-number" href="{{ paginator.paginate_path | replace: ':num', page }}">{{ page }}</a>
        {% endif %}
      {% endfor %}
      {% if paginator.next_page %}
        <a href="{{ paginator.next_page_path | relative_url }}">Next &raquo;</a>
      {% endif %}
    </nav>
  {% endif %}

</section>

