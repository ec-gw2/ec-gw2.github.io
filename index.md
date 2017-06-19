---
---

# eC Raid runs

This page will automatically, update with all the new runs as they are updated.

{% for item in site.static_files | sort: "path"  %}
  {% assign path = item.path | split:"/" %}
  {% for a in path %}
    {{a}}
  {% endfor %}
  {% if path[0] == "assets" %}
    {% continue %}
  {% endif %}
  {% assign name = item.path | remove_first:"/" | replace_first:"/","-" | remove:".html" %}
 * [{{ name }}]({{ item.path }})
{% endfor %}
