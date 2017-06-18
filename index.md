---
---

{% for item in site.static_files %}
  {{ item.path }}
{% endfor %}
