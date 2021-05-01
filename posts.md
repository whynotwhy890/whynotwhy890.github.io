---
layout: default
title: Posts
---
<ul class="site-category">
    {% assign pages_list = site.pages %}
    {% for node in pages_list %}
      {% if node.title != null %}
        {% if node.layout == "category" %}
          <li><a class="category-link {% if page.url == node.url %} active{% endif %}"
          href="{{ site.baseurl }}{{ node.url }}">{{ node.title }}</a></li>
        {% endif %}
      {% endif %}
    {% endfor %}
    
</ul>

<div id="posts">
  <h1>Posts</h1>
  <ul class="posts noList">
    {%- for post in site.posts -%}
      <li>
      	<span class="date">{{ post.date | date_to_string }}</span>
      	<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      	<p class="description">{%- if post.description -%}{{ post.description  | strip_html | strip_newlines | truncate: 120 }}{%- else -%}{{ post.content | strip_html | strip_newlines | truncate: 120 }}{%- endif -%}</p>
      </li>
    {%- endfor -%}
  </ul>
</div>
