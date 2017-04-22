---
layout: page
title: Podcasts
---
{% for podcast-category in site.podcast-categories %}
  <h1 class="post-title"> {{ podcast-category}} </h1>
  <ul class="post-list">
    {% for post in site.podcasts %}
    {% if post.categories contains podcast-category %}
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
