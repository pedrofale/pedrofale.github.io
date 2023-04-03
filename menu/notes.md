---
layout: default
title: Notes
---

## Notes

<ul class="posts">
  {% for post in site.posts %}
    {% if post.published %}
    <li itemscope>
    <div class="post-list-text">
     <a id="post-list-img" href="{{ site.github.url }}{{ post.url }}"><img src="{{ site.github.url }}/assets/img/{{ post.img }}"></a>
        <a class="post-list-title" href="{{ site.github.url }}{{ post.url }}">{{ post.title }}</a>
        <p class="post-date">
        {{ site.data.settings.post_date_prefix }}
          {% assign d = post.date | date: "%-d"  %}
          {{ post.date | date: "%B" }}
          {% case d %}
            {% when '1' or '21' or '31' %}{{ d }}st,
            {% when '2' or '22' %}{{ d }}nd,
            {% when '3' or '23' %}{{ d }}rd,
            {% else %}{{ d }}th,{% endcase %}
          {{ post.date | date: "%Y" }}         
        </p>
        <p class="post-list-subtitle">{{ post.subtitle }}</p>
     </div>
    </li>
    <br><br>
    {% endif %}
  {% endfor %}
</ul>
