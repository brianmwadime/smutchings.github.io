---
layout: index
title: Projects - Sam Hutchings - Artist and Designer
meta-description: Passionate about creating a better world for everyone, through making great experiences. Open to opportunities.
---

<section id="s-hello">
  <div class="container" id="c-hello">
    <h1>Projects</h1>
    <h2>The projects I've undertaken thus far.</h2>
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
      {% for post in site.projects %}
        <li>
          <a href="{{ post.url }}">{{ post.title }}</a>
        </li>
      {% endfor %}
    </ul>
  </div>
</section>
