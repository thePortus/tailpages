---
layout: page
title: Blog
permalink: blog
---

{% if site.paginate %}
  {% assign posts = paginator.posts %}
{% else %}
  {% assign posts = site.posts %}
{% endif %}

<div>
  {% for post in site.posts %}
    <div class="py-1">
      <h3><a href="{{site.baseurl}}{{ post.url }}">{{ post.title}}</a></h3>
      <div class="text-sm text-gray-400">{{post.date | date: "%B %-d, %Y"}}</div>
    </div>
  {% endfor %}
</div>

{% if site.paginate %}
  <div class="pager">
    <ul class="pagination">
    {%- if paginator.previous_page %}
      <li><a href="{{ paginator.previous_page_path | relative_url }}" class="previous-page">{{ paginator.previous_page }}</a></li>
    {%- else %}
      <li><div class="pager-edge">•</div></li>
    {%- endif %}
      <li><div class="current-page">{{ paginator.page }}</div></li>
    {%- if paginator.next_page %}
      <li><a href="{{ paginator.next_page_path | relative_url }}" class="next-page">{{ paginator.next_page }}</a></li>
    {%- else %}
      <li><div class="pager-edge">•</div></li>
    {%- endif %}
    </ul>
  </div>
{%- endif %}