---
layout: page
title: Portfolio
permalink: /portfolio/
meta-description: I've worked with all sorts of companies and people to hone their communication and experience. See a selection here.
---

<ul class="img-grid">

    <li class="img-grid__item">
        <a href="http://samhutchings.co/hireme/">
        <img src="/img/portfoliohireme.png">

            <div class="img-grid__overlay">
              <h1>Hire Me</h1>
              <p>Click to find out more.</p>
            </div>
        </a>
      </li>

{% for project in site.portfolio %}
  
    {% if project.redirect %}
      <li class="img-grid__item">
        <a href="{{ project.redirect }}">
            {% if project.img %}
              <img src="{{ project.img }}">
            {% else %}
              <div class="thumbnail blankbox"></div>
            {% endif %}

            <div class="img-grid__overlay">
              <h1>{{ project.title }}</h1>
              <p>{{ project.description }}</p>
            </div>
        </a>
      </li>

    {% else %}

      <li class="img-grid__item">
        <a href="{{ site.baseurl }}{{ project.url }}">
            {% if project.img %}
              <img src="{{ project.img }}">
            {% else %}
              <div class="thumbnail blankbox"></div>
            {% endif %}

            <div class="img-grid__overlay">
              <h1>{{ project.title }}</h1>
              <p>{{ project.description }}</p>
            </div>
        </a>
      </li>
      
    {% endif %}

{% endfor %}

</ul>
