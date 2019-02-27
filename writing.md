---
layout: page
title: Writing - Sam Hutchings - Artist and Designer
h1: Writing
h2: My writing and ideas on Art and Design.
---

<section id="s-designingTheFuture">
  <div class="container" id="c-designingTheFuture">
    <h3>Coming Soon</h3>
    <ul>
      {% for post in site.posts %}
        <li>
          <a href="{{ post.url }}">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
  </div>
</section>
