---
---

# eC Raid runs

This page will automatically, update with all the new runs as they are updated.
> Last updated: {% last_modified_at %}

{% assign non_assets = site.static_files | where: "asset", false %}
{% for item in non_assets %}
 * [{{ item.path }}]({{ item.path }})
{% endfor %}

