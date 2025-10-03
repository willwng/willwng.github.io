---
layout: default
title: Blog
permalink: /blog/
description:
nav: true
nav_order: 5
pagination:
  enabled: true
  collection: posts
---
<p>I'll write half-baked scientific thoughts here</p>


<div class="post">

  <ul class="post-list">

    {% for post in site.posts %}

    {% assign year = post.date | date: "%Y" %}
    {% assign tags = post.tags | join: "" %}
    {% assign categories = post.categories | join: "" %}

    <li>
        <h3>
        {% if post.redirect == blank %}
          <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
        {% endif %}
      </h3>
      <p>
      {{ post.description }}
      </p>
      <p class="post-meta">
        {{ post.date | date: '%B %d, %Y' }}
      </p>

    </li>

    {% endfor %}

  </ul>

</div>
