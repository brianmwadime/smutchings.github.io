---
layout: page
title: Projects - Sam Hutchings - Artist and Designer
h1: Projects
h2: My work so far.
---

<section id="s-designingTheFuture">
  <div class="container" id="c-designingTheFuture">
    <ul>
      {% for post in site.projects %}
        <li>
          <a href="{{ post.url }}">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
  </div>
</section>
