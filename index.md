---
---

# eC Raid runs

{% assign year_group = '' %}
{% assign month_group = '' %}
{% assign day_group = '' %}

## Boss Kills

<table id='ec-boss' style="cursor: pointer;" >
  <thead>
    <tr>
      <td data-sort-default>Date</td>
      <td>Boss</td>
    </tr>
  </thead>
  <tbody>
{% for item in site.static_files %}

{% assign path = item.path | split:"/" %}

{% if path[0] == "EVTC Logs" %}
  {% continue %}
{% endif %}

{% if path[0] == "assets" %}
  {% continue %}
{% endif %}
{% unless path[1] == year_group %}
{% capture year_group %}{{path[1]}}{% endcapture %}
{% endunless %}

{% unless path[2] == month_group %}
{% capture month_group %}{{path[2]}}{% endcapture %}
{% endunless %}

{% unless path[3] == day_group %}
{% capture day_group %}{{path[3]}}{% endcapture %}
{% endunless %}
{% assign name = item.path | remove_first:"/" | replace:"/"," - " | remove:".html" %}

    <tr onclick="window.location='{{ item.path }}'">
      <td>{{year_group}}/{{month_group}}/{{day_group}}</td>
      <td>{{ path[4] | remove:".html" }} (click to view)</td>
    </tr>
{% endfor %}
  </tbody>
</table>

<script src="https://cdnjs.cloudflare.com/ajax/libs/tablesort/5.0.1/tablesort.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/tablesort/5.0.1/sorts/tablesort.date.min.js"></script>
<script>
  new Tablesort(document.getElementById('ec-boss'), {
   descending: true
  });
</script>
