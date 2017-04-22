---
layout: page
title: MOOCs
---
{% for mooc-category in site.mooc-categories %}
  <h1 class="post-title"> {{ mooc-category}} </h1>
  <ul class="post-list">
    {% for post in site.moocs %}
    {% if post.categories contains mooc-category %}
      <li>
        {% assign date_format = site.minima.date_format | default: "%b %-d, %Y" %}
        <span class="post-meta">{{ post.date | date: date_format }}</span>

        <h2>
          <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </h2>
      </li>
      {% endif %}
    {% endfor %}
  </ul>
{%endfor%}
