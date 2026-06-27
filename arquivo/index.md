---
layout: default
title: Arquivo
---

# Arquivo do Blog

Todos os artigos publicados, organizados por data.

{% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}

{% for year_group in posts_by_year %}
  <h2 style="font-family: var(--font-serif); font-size: var(--text-h2); margin-top: 3rem; margin-bottom: 1rem;">{{ year_group.name }}</h2>
  <ul style="list-style: none; padding: 0;">
    {% for post in year_group.items %}
      <li style="margin-bottom: 1rem;">
        <span style="font-family: var(--font-sans); font-size: var(--text-sm); color: var(--gray-600);">{{ post.date | date: "%d %b" }}</span>
        <span style="margin: 0 0.5rem;">•</span>
        <a href="{{ post.url | relative_url }}" style="font-family: var(--font-serif); color: var(--gray-950); text-decoration: none;">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
{% endfor %}

## Por Categoria

{% assign unique_categories = site.posts | map: "categories" | join: "," | split: "," | uniq %}

<ul style="list-style: none; padding: 0; margin-top: 2rem;">
  {% for category in unique_categories %}
    <li style="margin-bottom: 0.5rem;">
      <strong style="color: var(--gray-950);">{{ category }}</strong>
    </li>
  {% endfor %}
</ul>
