---
layout: page
title: 同人誌
---
<ul>
  {% for book in site.books %}
    <li>
      <h2><a href="{{ book.url | relative_url }}">{{ book.name }}</a></h2>
      <p>発行日:{{ book.date_of_issue }}</p>
    </li>
  {% endfor %}
</ul>
