---
layout: default
---

<div class="posts">
  {% assign poems = (site.posts sort: "date_info") | reverse %}
  {% for poem in poems%}
  <p>
  <div class="post">
    <h2 class="post-title">
    {{ poem.title }}
      <!-- <a href="{{ poem.url }}"> {{ poem.title }}  </a>
       -->
    </h2>
    {% if poem.date %}
    <div class="post-date">{{ poem.date_info }}</div>
    {% endif %}

    <pre>
{{ poem.content }}
    </pre>
    </div>
  </p>
  {% endfor %}
</div>
