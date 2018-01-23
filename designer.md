---
layout: default
title: Samuel Hutchings - Designer
permalink: /designer
meta-description: Designer Portfolio.
---
<div class="container-fluid">

      {% for project in site.designer %}
        <div class="card">
          <img class="card-img-top" src="{{ project.img }}" alt="{{ project.title }}">
          <div class="card-body">
            <h5 class="card-title">{{ project.title }}</h5>
            <p class="card-text">{{ project.description }}</p>
            <a href="{{ project.url }}" class="btn btn-block btn-outline-primary btn-lg">Read more</a>
          </div>
        </div>

      {% else %}

      {% endfor %}
      
  </div>
