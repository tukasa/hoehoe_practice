---
short_name: tukasa
name: tukasa hiiragi
---

{% assign image_files = site.static_files | where: "image", true %}
{% for myimage in image_files %}
 {{ myimage.name }}
 {{ page.short_name }}.jpg
  ![image]({{ myimage.path | absolute_url }}){: .img-responsive}
{% endfor %}

生年月日：7月7日
星座：蟹座
誕生石：ルビー
誕生花：クチナシ
