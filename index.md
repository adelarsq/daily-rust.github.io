---
layout: default
title: Daily notes about Rust language
---

# [Daily Rust](http://daily-rust.github.io)

Daily notes about [Rust language](https://www.rust-lang.org).

Rust is a modern systems programming language focusing on safety, speed, and concurrency. It accomplishes these goals by being memory safe without using garbage collection.

<ul class="posts">
  {% for post in site.posts reversed %}
    {% if post.tags contains "about" %}
    <li><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.index_title }}</a> ({{ post.date | date_to_string }})</li>
    {% endif %}
  {% endfor %}
</ul>

**Articles:**

<ul class="posts">
  {% for post in site.posts reversed %}
    {% if post.tags contains "article" %}
    <li><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.index_title }}</a> ({{ post.date | date_to_string }})</li>
    {% endif %}
  {% endfor %}
</ul>

**Beginner:**

<ul class="posts">
  {% for post in site.posts reversed %}
    {% if post.tags contains "beginner" %}
    <li><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.index_title }}</a> ({{ post.date | date_to_string }})</li>
    {% endif %}
  {% endfor %}
</ul>

**Intermediate:**

<ul class="posts">
  {% for post in site.posts reversed %}
    {% if post.tags contains "intermediate" %}
    <li><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.index_title }}</a> ({{ post.date | date_to_string }})</li>
    {% endif %}
  {% endfor %}
</ul>

**Advanced:**

<ul class="posts">
  {% for post in site.posts reversed %}
    {% if post.tags contains "advanced" %}
    <li><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.index_title }}</a> ({{ post.date | date_to_string }})</li>
    {% endif %}
  {% endfor %}
</ul>

**Algorithms:**

<ul class="posts">
  {% for post in site.posts reversed %}
    {% if post.tags contains "algorithm" %}
    <li><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.index_title }}</a> ({{ post.date | date_to_string }})</li>
    {% endif %}
  {% endfor %}
</ul>
