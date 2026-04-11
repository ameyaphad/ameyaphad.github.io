---
layout: single
title: "Work Experience"
permalink: /experience/
author_profile: true
---

{% for exp in site.data.experience %}
  {% include experience-entry.html exp=exp %}
{% endfor %}
