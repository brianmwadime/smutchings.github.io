---
layout: page
title: portfolio
permalink: /portfolio/
---

{% for project in site.portfolio %}
  
  <ul class="img-grid">

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
    
    </ul>

{% endfor %}
