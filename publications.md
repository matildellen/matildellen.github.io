---
layout: default
title: Publications
---

# Publications

Authors with **my name** appear in bold.

<div class="pub-list">

{% assign pubs = site.data.publications | sort: "year" | reverse %}

{% assign current_year = "" %}

{% for pub in pubs %}

{% if pub.year != current_year %}
<h3 class="pub-year">{{ pub.year }}</h3>
{% assign current_year = pub.year %}
{% endif %}

<p>
  {{ pub.authors }} ({{ pub.year }}).
  <i>{{ pub.title }}</i>.
  {{ pub.journal }}.
  {% if pub.doi %}
    <a class="pub-link" href="{{ pub.doi }}" target="_blank">DOI</a>
  {% endif %}
  {% if pub.pdf %}
    <a class="pub-link" href="{{ pub.pdf }}" target="_blank">PDF</a>
  {% endif %}
  {% if pub.osf %}
    <a class="pub-link" href="{{ pub.osf }}" target="_blank">OSF</a>
  {% endif %}
</p>

{% endfor %}

</div>
