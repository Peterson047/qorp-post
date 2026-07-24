---
layout: default
title: Arquivo
---

<div class="page-header">
  <h1>Arquivo</h1>
  <p>Todos os artigos, organizados por data.</p>
</div>

{% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}

{% for year_group in posts_by_year %}
  <h2 class="archive-year">{{ year_group.name }}</h2>
  <ul class="archive-list">
    {% for post in year_group.items %}
      <li class="archive-entry">
        <span class="archive-date">{{ post.date | date: "%d %b" }}</span>
        <a href="{{ post.url | relative_url }}" class="archive-link">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}

<div class="archive-cats">
  <h2>Categorias</h2>
  {% assign unique_categories = site.posts | map: "categories" | join: "," | split: "," | uniq %}
  <div class="cat-row">
    {% for category in unique_categories %}
      <span class="pill">{{ category }}</span>
    {% endfor %}
  </div>
</div>
