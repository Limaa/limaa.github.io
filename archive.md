---
title: Archive
permalink: /archive
---

<div class="archive">
  {%- for post in site.posts -%}
    {%- if post.next -%}
      {%- assign year = post.date | date: '%Y' -%}
      {%- assign prev_year = post.next.date | date: '%Y' -%}
      {%- if year != prev_year -%}
        <h2>{{ post.date | date: '%Y' }}</h2>
      {%- endif -%}
      {%- assign month = post.date | date: '%B' -%}
      {%- assign prev_month = post.next.date | date: '%B' -%}
      {%- if month != prev_month -%}
        <h3>{{ post.date | date: '%B' }}</h3>
      {%- endif -%}
    {%- else -%}
      <h2>{{ post.date | date: '%Y' }}</h2>
      <h3>{{ post.date | date: '%B' }}</h3>
    {%- endif -%}
    <h4><a href="{{ post.url }}">{{ post.title }}</a></h4>
  {%- endfor -%}
</div>
