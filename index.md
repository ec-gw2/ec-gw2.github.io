---
---

# eC Raid runs

This page will automatically, update with all the new runs as they are updated.

{% for item in site.static_files  %}
  {{ item.path | split:"/" }}
 * [{{ item.path | remove_first:"/" | replace_first:"/","-" }}]({{ item.path }})
{% endfor %}
