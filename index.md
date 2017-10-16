---
layout: default
---

{% assign poems = site.poems | sort: "path" %}

<ul class="posts">
  {% for poem in poems%}
  <li>
    <a href="#{{poem.title | slugify}}"> {{ poem.title }} </a>
  </li>
  {%endfor%}
</ul>

<div class="posts">
  {% for poem in poems%}
  <a name="{{poem.title | slugify}}"></a>
  <p>
  <div class="post">
    <h2 class="post-title">
    {{ poem.title }}
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

<footer>
  Kontakt: <script language="JavaScript">
  var username = "tomas.kozelek";
  var hostname = "gmail.com";
  var full_email = username + "@" + hostname ;
  document.write(full_email);
  </script>
</footer>
