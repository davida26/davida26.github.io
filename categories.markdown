---
layout: page
title: Topics
permalink: /topics-collection/
description: View all categories and articles on CuratedCode.com
sitemap: false
---

<div class="page">
  <h1 class="page-title">{{title}}</h1>
  <p>A collection of topics, otherwise called categories.</p>
      <ul class="message">
      {% assign categories =  (site.categories | sort %}
      <p>Jump to a Topic</p>
      {% for category in categories %}
       <li>
          <a href="#{{ category | first | slugify }}">
                  {{ category[0] | replace:'-', ' ' }} ({{ category | last | size }})
          </a>
      </li>
      {% endfor %}
      </ul>

    <div class="cat-list">
      {% for category in categories %}
      <a name="{{ category[0] }}"></a>
      <h2>
      {{ category[0] | replace:'-', ' ' }} ({{ category | last | size }}) </h2>
      {% assign sorted_posts = site.posts | sort: 'title' %}
      {% for post in sorted_posts %}
      {%if post.categories contains category[0]%}

      
        <h3><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h3>
         <p>{{ post.description | strip_html | truncate: 160 }}</p>

      {%endif%}
      {% endfor %}

      {% endfor %}
    </div>
</div>
