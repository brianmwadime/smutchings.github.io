---
layout: page
title: Writing - Sam Hutchings - Artist and Designer
---

<section id="s-topper">
  <div class="container" id="c-topper">
    <h1>Writing</h1>
    <h2>My writing and ideas on Art and Design.</h2>
  </div>
</section>
<section id="s-nav">
  <div class="container" id="c-nav">
    <nav>
      {% include nav.html %}
    </nav>
  </div>
</section>
<section id="s-designingTheFuture">
  <div class="container" id="c-designingTheFuture">
    <ul>
      {% for post in site.posts %}
        <li>
          <a href="{{ post.url }}">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
  </div>
</section>
