---
layout: page
title: Archive
---
<ul class="posts">
  {% for post in site.posts %}

    {% unless post.next %}
      <h3>{{ post.subject }}</h3>
    {% else %}
      {% capture sub %}{{ post.subject }}{% endcapture %}
      {% capture nsub %}{{ post.next.subject }}{% endcapture %}
      {% if sub != nsub %}
        <h3>{{ post.subject }}</h3>
      {% endif %}
    {% endunless %}

    <li itemscope>
      <a href="{{ site.github.url }}{{ post.url }}">{{ post.title }}</a>
      <p class="post-date"><span><i class="fa fa-calendar" aria-hidden="true"></i> {{ post.date | date: "%B  %Y" }} </span></p>
    </li>

  {% endfor %}
</ul>
