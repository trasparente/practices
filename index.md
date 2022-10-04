---
title: Practices
---
<div class="center" markdown='1'>
![8 limbs]({{ '/assets/images/8_limbs.svg' | absolute_url }})
</div>
{% include widgets/csv-blocks.html file='practices' %}
{% include widgets/csv-counter.html file='practices' days='7' title='Week' %}
{% include widgets/csv-counter.html file='practices' days='30' title='Month' %}
{% include widgets/csv-counter.html file='practices' days='182' title='Six months' %}
{% include widgets/csv-counter.html file='practices' days='365' title='Year' %}
{%- assign now = site.time | date: "%s" -%}
{%- assign days = site.data.practices | sort: 'date' | first | map: 'date' | first | date: "%s" | minus: now | abs | divided_by: 86400 -%}
{%- assign title = days | divided_by: 365.0 | round: 1 | append: ' Years' -%}
{% include widgets/csv-counter.html file='practices' days=days title=title %}