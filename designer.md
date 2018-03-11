---
layout: default
title: Samuel Hutchings - Designer
permalink: /designer
meta-description: Designer Portfolio.
---
<div class="container-fluid">
  <div class="row d-flex align-items-center justify-content-center flex-column">
    <div class="col topMargin">
      {% for project in site.designer reversed %}
        <div class="card">
          <img class="card-img-top" src="{{ project.img }}" alt="{{ project.title }}">
          <div class="card-body">
            <h5 class="card-title">{{ project.title }}</h5>
            <p class="card-text">{{ project.description }}</p>
            <a href="{{ project.url }}" class="btn btn-block btn-primary btn-lg">Read more</a>
          </div>
        </div>

      {% else %}

      {% endfor %}
      </div>
    </div>
  </div>
