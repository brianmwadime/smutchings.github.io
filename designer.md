---
layout: default
title: Samuel Hutchings - Designer
permalink: /designer
meta-description: Designer Portfolio.
---

  <div class="container">
  <div class="row full-height">
    <div class="col-lg-7 col-left-scroll">

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
    <div class="col-lg-5 fixed-right-desktop">
      <header class="cd-auto-hide-header">
        <nav class="navigation cd-primary-nav">
          <ul>
            <li><a href="/index.html" title="Go home">Home</a></li>
            <li><a href="/designer" title="View my portfolio">Designer</a></li>
            <li><a href="https://www.medium.com/@Smutchings" title="Read my writings on Medium">Writer</a></li>
            <li><a href="https://www.twitter.com/Smutchings" title="View my Twitter">Tweeter</a></li>
          </ul>
        </nav>
      </header>
    </div>
  </div>
</div>
