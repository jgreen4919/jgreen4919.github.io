---
layout: archive
title: "Notes"
permalink: /notes/
author_profile: true
---

 <div class="wordwrap">I don't blog very much, but I keep miscellaneous writing on this page.</div>

{% include base_path %}

{% for post in site.posts reversed %}
  {% include archive.html %}
{% endfor %}
