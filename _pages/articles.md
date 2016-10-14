---
layout: page
title: Taxidea
subtitle: The blog of Victoria Badger
desc: Notes from a busy life
permalink: /blog/
---
<ul class="post-list">
  {% for post in site.categories.blog %}
  <li class="post">
    <a class="post-link" href="{{ post.url | prepend: site.baseurl }}">
      <h4 class="post-title">{{ post.title }}</h4>
      <time class="post-date" datetime="{{ post.date }}">
      {% assign d = post.date | date: "%-d" %}
      {% assign m = post.date | date: "%B" %}
      {% case m %}
        {% when 'April' or 'May' or 'June' or 'July' %}{{ m }}
        {% when 'September' %}Sept.
        {% else %}{{ post.date | date: "%b" }}.
        {% endcase %}
      {% case d %}
        {% when '1' or '21' or '31' %}{{ d }}st{% when '2' or '22' %}{{ d }}nd{% when '3' or '23' %}{{ d }}rd{% else %}{{ d }}th{% endcase %},
      {{ post.date | date: "%Y" }}
      </time>
      <p class="post-desc">{% if post.desc %}{{ post.desc }}{% else %}{{ post.excerpt }}{% endif %}</p>
    </a>
  </li>
  {% endfor %}
</ul>
<!-- post-list -->
