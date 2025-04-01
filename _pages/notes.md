---
layout: archive
title: "Notes"
permalink: /notes/
author_profile: true
---

 <div class="wordwrap">I don't blog very much, but I keep miscellaneous writing on this page.</div>

{% include base_path %}

{% for post in site.posts reversed %}
  <li>
      <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      <p>{{ post.excerpt }}</p>
      <a href="{{ post.url }}">Read more →</a>
    </li>
{% endfor %}
