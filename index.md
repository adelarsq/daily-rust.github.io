---
layout: default
title: Daily notes about Rust language
---

# [Daily Rust](http://daily-rust.github.io)

Daily notes about Rust language.

<ul class="posts">
  {% for post in site.posts reversed %}
    {% if post.tags contains "rustposts" %}
    <li><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.index_title }}</a> ({{ post.date | date_to_string }})</li>
    {% endif %}
  {% endfor %}
  <li>1: Intro</li>
</ul>
