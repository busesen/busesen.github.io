---
layout: single
title: "Service"
permalink: /service/
author_profile: true
classes:
  - service-page
---

## Journal Reviewing

{% if site.data.service.journals and site.data.service.journals.size > 0 %}
<ul class="service-list">
{% for journal in site.data.service.journals %}
  <li class="service-item">
    <span class="service-name">{{ journal.name }}</span>
    {% if journal.url %}<a class="course-arrow" href="{{ journal.url }}" aria-label="Open the {{ journal.name }} website">&#8599;</a>{% endif %}
  </li>
{% endfor %}
</ul>
{% endif %}
