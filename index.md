---
---

# eC Raid runs

This page will automatically, update with all the new runs as they are updated.

{% for item in site.static_files  %}
  {% assign path = item.path | split:"/" %}
  {% if path[1] == "assets" %}
    {% continue %}
  {% endif %}
  {% assign name = item.path | remove_first:"/" | replace_first:"/","-" | remove:".html" %}
 * [{{ name }}]({{ item.path }})
{% endfor %}
