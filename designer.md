---
layout: default
title: Sam Hutchings - Budding Product Designer
permalink: /designer
meta-description: Passionate about creating a better world for everyone, through making great products.
---
<div class="container-fluid">
  <div class="row d-flex align-items-center justify-content-center flex-column">
    <div class="col topMargin">
      {% for project in site.designer reversed %}
        <div class="card">
          <video class="card-img-top" poster="{{ project.img }}" autoplay loop muted>
            <source src="{{ project.video }}" type="video/mp4">
          </video>
          <div class="card-body">
            <h1 class="card-title">{{ project.title }}</h1>
            <h2 class="card-subtitle mb-2 text-muted">{{ project.subtitle }}</h2>
            <p class="card-text">{{ project.description }}</p>
            <a href="{{ project.url }}" class="btn btn-block btn-primary btn-lg">{{ project.button-text }}</a>
          </div>
        </div>

      {% else %}

      {% endfor %}
      </div>
    </div>
  </div>
