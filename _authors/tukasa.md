---
short_name: tukasa
name: tukasa hiiragi
---

{% assign image_files = site.static_files | where: "image", true %}
{% for myimage in image_files %}
  {{ myimage.basename }}
  {{ page.short_name }}
  {%- if myimage.basename == page.short_name -%}
    <img src="{{ myimage.path | absolute_url }}" class ="img-responsive">
  {%- endif -%}
{% endfor %}


生年月日：7月7日
星座：蟹座
誕生石：ルビー
誕生花：クチナシ
