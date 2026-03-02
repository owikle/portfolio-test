---
title: Blog
nav: Blog
nav_order: 4
---
  

{% assign posts = site.posts %}
 


  {%- if posts.size > 0 -%}
    {%- if page.list_title -%}
      <h2 class="post-list-heading">{{ page.list_title }}</h2>
    {%- endif -%}
    <ul class="post-list">
      {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
      {%- for post in posts -%}
      <li class="post-item" style="padding: 1em">
        <div class="post-content">
          <span class="post-meta">{{ post.date | date: date_format }}</span>
          <h3>
            <a class="post-link" href="{{ post.url | relative_url }}">
              {{ post.title | escape }}
            </a>
          </h3>
          {% if post.image %}
          <img src="{{ '/assets/' | append: post.image | relative_url }}" class="blog-roll-image"> 
          {% endif %}
          {%- if site.show_excerpts -%}
            {{ post.excerpt }}
          {%- endif -%}
        </div>
      </li>
      {%- endfor -%}
    </ul>


  {%- endif -%}
