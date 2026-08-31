---
permalink: /
title: "About me"
author_profile: true
classes:
  - about-page
redirect_from: 
  - /about/
  - /about.html
---

Hi! I am a PhD candidate in the [Risk Analytics and Optimization Lab](https://www.epfl.ch/labs/rao/) at EPFL, where I am fortunate to be advised by Prof. [Daniel Kuhn](https://people.epfl.ch/daniel.kuhn?lang=en). My research focuses on scalable algorithms for decision-making under uncertainty, with a focus on robust optimization, sequential stochastic planning, and efficient estimation methods.
{: .about-lead}

Previously, I obtained my MSc and BSc in Industrial Engineering from Bilkent University, where I worked under the supervision of [Mustafa Çelebi Pınar](https://www.ie.bilkent.edu.tr/~mustafap/).

<section id="research" class="home-section research-section" aria-labelledby="research-heading">
  <h2 id="research-heading">Research</h2>

  {% assign publications = site.publications | sort: "date" | reverse %}
  <div class="research-list">
    {% for post in publications %}
      {% assign publication_url = post.link | default: post.url %}
      <article class="research-item">
        <a class="research-link" href="{{ publication_url }}">
          <span class="research-arrow" aria-hidden="true">&#8599;</span>
          <span class="research-content">
            <span class="research-title">{{ post.title }}</span>
            <span class="research-meta">
              {{ post.authors }}, <em>{{ post.venue }}</em>, {{ post.date | date: "%Y" }}
            </span>
          </span>
        </a>
      </article>
    {% endfor %}
  </div>
</section>

<section id="news" class="home-section news-section" aria-labelledby="news-heading">
  <h2 id="news-heading">News</h2>

  <div class="news-panel">
    <div class="news-list">
      <div class="news-item">
        <span class="news-date">April 2026</span>
        <p>Our paper <a href="https://arxiv.org/abs/2604.14075">Multistage Conditional Compositional Optimization</a> is online.</p>
      </div>
    </div>
  </div>
</section>

<section id="teaching" class="home-section teaching-section" aria-labelledby="teaching-heading">
  <h2 id="teaching-heading">Teaching</h2>

  <div class="teaching-group">
    <div class="teaching-group__header">
      <h3>EPFL</h3>
      <span>Teaching Assistant</span>
    </div>
    <ul class="course-list">
      <li class="course-item">
        <a class="course-name" href="https://edu.epfl.ch/coursebook/en/convex-optimization-MGT-418">Convex Optimization</a>
        <span class="course-term">Fall 2023, 2024, 2025, 2026</span>
      </li>
      <li class="course-item">
        <a class="course-name" href="https://edu.epfl.ch/coursebook/en/optimal-decision-making-MGT-483">Optimal Decision Making</a>
        <span class="course-term">Spring 2024</span>
      </li>
    </ul>
  </div>

  <div class="teaching-group">
    <div class="teaching-group__header">
      <h3>Bilkent University</h3>
      <span>Teaching Assistant</span>
    </div>
    <ul class="course-list">
      <li class="course-item">
        <span class="course-name">Engineering Economic Analysis</span>
        <span class="course-term">Fall and Spring 2022</span>
      </li>
      <li class="course-item">
        <span class="course-name">Modelling and Methods in Optimization</span>
      </li>
    </ul>
  </div>
</section>
