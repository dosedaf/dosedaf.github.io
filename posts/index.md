---
layout: page
title: Posts
---
<section id="bits">
  {% assign bits = site.bits | sort: "date" | reverse %}
  {% for bit in bits %}
  <article class="bit">
    <time datetime="{{ bit.date | date_to_xmlschema }}">{{ bit.date | date: "%b %-d, %Y · %H:%M" }}</time>
    <div class="bit-text">{{ bit.content }}</div>
  </article>
  {% endfor %}
</section>
