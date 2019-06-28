---
layout: page
title: Tags
permalink: /tags/
---

<ul class="tag-cloud">
{% for tag in site.tags %}
  <span style="font-size: {{ tag | last | size | times: 100 | divided_by: site.tags.size | plus: 75  }}%">
    <a href="#{{ tag | first | slugize | downcase }}">
      {{ tag | first | downcase}}
    </a> &nbsp;&nbsp;
  </span>
{% endfor %}
</ul>
<br>


{% for tag in site.tags %}
  {% capture tag_name %}{{ tag | first }}{% endcapture %}
  <h2 id="{{ tag_name | downcase }}">{{ tag_name | downcase}}</h2>

  <ul class="posts-list">
  {% for post in site.tags[tag_name] %}
    <li>
      <strong>
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </strong>
      <span class="post-date">- {{ post.date | date_to_long_string }}</span>
    </li>
  {% endfor %}
  </ul>
  {% if forloop.last == false %}<hr>{% endif %}
{% endfor %}
<br>