---
---

# eC Raid runs

{% assign year_group = '' %}
{% assign month_group = '' %}
{% assign day_group = '' %}


{% for item in site.static_files | reverse  %}
  {{item.path}}
{% endfor %}

{% for item in site.static_files %}
  {{item.path}}
{% endfor %}

{% for item in site.static_files | sort: "path" | reverse  %}

{% assign path = item.path | split:"/" %}

{% if path[0] == "EVTC Logs" %}
  {% continue %}
{% endif %}

{% if path[0] == "assets" %}
  {% continue %}
{% endif %}

{% unless path[1] == year_group %}
{% capture year_group %}{{path[1]}}{% endcapture %}
## {{year_group}}
{% endunless %}

{% unless path[2] == month_group %}
{% capture month_group %}{{path[2]}}{% endcapture %}
### {{month_group}}
{% endunless %}

{% unless path[3] == day_group %}
{% capture day_group %}{{path[3]}}{% endcapture %}
#### {{day_group}}
{% endunless %}
  
{% assign name = item.path | remove_first:"/" | replace:"/"," - " | remove:".html" %}
 * [{{ name }}]({{ item.path }})
{% endfor %}
