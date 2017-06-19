---
---

# eC Raid runs

fuck you BURGER.

{% assign date_group = '' %}
{% for item in site.static_files | sort: "modified_time"  %}
  {% assign path = item.path | split:"/" %}
  {% if path[0] == "EVTC Logs" %}
    {% continue %}
  {% endif %}
  {% if path[0] == "assets" %}
    {% continue %}
  {% else %}
  {% unless path[0] == date_group %}
    {% capture date_group %}{{path[0]}}{% endcapture %}
    ## {{date_group}}
  {% endunless %}
  {% endif %}
  
  {% assign name = item.path | remove_first:"/" | replace_first:"/"," - " | remove:".html" %}
 * [{{ name }}]({{ item.path }})
{% endfor %}
