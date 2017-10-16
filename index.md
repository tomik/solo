---
layout: default
---

{% assign poems = site.poems | sort: "path" | reverse%}

<ul class="posts" style="margin-bottom: 3rem;">
  {% for poem in poems%}
  <li>
    <a href="#{{poem.title | slugify}}"> {{ poem.title }} </a>
  </li>
  {%endfor%}
</ul>



<div class="posts">
  {% for poem in poems%}
  <a name="{{poem.title | slugify}}"></a>
  <p class="post">
    <h2 class="post-title"> {{ poem.title }} </h2>
    <div class="post-date" style="margin-bottom: 1rem;">
    {% if poem.date_info %} {{ poem.date_info }}, {% endif %}
    {% if poem.place %} {{poem.place}} {% endif %}
    </div>

    <pre>
{{ poem.content | remove: '<p>' | remove: '</p>' }}
    </pre>
    </p>
  {% endfor %}
</div>

<footer style="margin-top:2rem; padding-bottom: 1.5rem;">
  Kontakt: <script language="JavaScript">
  var username = "tomas.kozelek";
  var hostname = "gmail.com";
  var full_email = username + "@" + hostname ;
  document.write(full_email);
  </script>
</footer>
