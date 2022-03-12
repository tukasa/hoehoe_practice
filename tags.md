---
layout: page
title: tags
---

{% comment %}
<!--
- Create an empty array.
- Obtain a tag name and push it to the array.
- Sort the tag names.
- List tags as a tag cloud.
-->
{% endcomment %}
{% assign tag_names = "" | split: "|"  %}
{% for posts_by_tag in site.tags %}
  {% assign tag_names = tag_names | push: posts_by_tag.first %}
{% endfor %}
{% assign tag_names = tag_names | sort %}

<article class="post">
  <header class="post-header">
    <div class="post-title">Tag</div>
  </header>
  <div class="post-content">
    <div id="archives">
    {% include tag_cloud.html tag_names=tag_names %}
    <hr>
    {% for tag_name in tag_names %}
    <div>
      <h3 id="{{ tag_name }}">
        {{ tag_name | capitalize | replace: "_", " " }}
      </h3>
      {% for post in site.tags[tag_name] %}
        {{ post.date | date: "%Y/%m/%d" }} <a href="{{ post.url | absolute_url }}">{{ post.title }}</a>
      {% endfor %}
    </div>
  {% endfor %}
    </div>
  </div>
</article>
