---
layout: page
title: Topics
permalink: /topics-collection/
description: View all categories and articles on CuratedCode.com
sitemap: false
---

<div class="page" id="category-page">
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
      <a name="{{ category[0]  | slugify }}"></a>
      <h2>
      {{ category[0] | replace:'-', ' ' }} ({{ category | last | size }}) </h2>
      {% assign sorted_posts = site.posts | sort: 'title' %}
      {% for post in sorted_posts %}
      {%if post.categories contains category[0]%}

      
        <h3><a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></h3>
         <p>{{ post.description | strip_html | truncate: 160 }}</p>
    
    <hr />

      {%endif%}
      {% endfor %}

      {% endfor %}
    </div>
</div>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.0/jquery.min.js"></script>

<script>
  $(function() {
  $('a[href*="#"]:not([href="#"])').click(function() {
    if (location.pathname.replace(/^\//,'') == this.pathname.replace(/^\//,'') && location.hostname == this.hostname) {
      var target = $(this.hash);
      target = target.length ? target : $('[name=' + this.hash.slice(1) +']');
      if (target.length) {
        $('html, body').animate({
          scrollTop: target.offset().top
        }, 1000);
        return false;
      }
    }
  });
});
</script>