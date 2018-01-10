---
layout: default
title: Samuel Hutchings - Designer
permalink: /designer/
meta-description: Designer Portfolio.
---

  <div class="container">
  <div class="row full-height">
    <div class="col-lg-7 col-left-scroll">

      {% for project in site.portfolio %}

        {% if project.redirect %}
        <div class="card">
          <img class="card-img-top" src="{{ project.img }}" alt="{{ project.title }}">
          <div class="card-body">
            <h5 class="card-title">{{ project.title }}</h5>
            <p class="card-text">{{ project.description }}</p>
            <a href="{{ project.redirect }}" class="btn btn-block btn-outline-primary">Go somewhere</a>
          </div>
        </div>

      {% else %}

      {% endfor %}

    </div>
    <div class="col-lg-5" style="position: fixed; right: 0%;">
      <!-- HTML for Home Page navigation-->
      <div id="home-navigation">
        <ul>
          <li><a href="/designer/">Designer</a></li>
          <li><a href="https://www.medium.com/@Smutchings" target="_blank">Writer</a></li>
          <li><a href="https://www.twitter.com/Smutchings" target="_blank">Tweeter</a></li>
        </ul>
      </div>
    </div>
  </div>
</div>