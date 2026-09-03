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

Hi! I am a PhD candidate in the [Risk Analytics and Optimization Lab](https://www.epfl.ch/labs/rao/) at EPFL, where I am fortunate to be advised by Prof. [Daniel Kuhn](https://people.epfl.ch/daniel.kuhn?lang=en). 

My research lies at the intersection of optimization, data science, and prescriptive analytics. I develop reliable and scalable algorithms that help decision-makers act under uncertainty, particularly in sequential settings where choices must be made before all relevant information is available. A central question in my work is how to account for uncertainty in data and models without sacrificing the speed and scale required in practice. I address this question through distributionally robust optimization, which safeguards decisions when historical data provide an incomplete picture of future conditions, and efficient sampling methods, including multilevel Monte Carlo, which make complex multistage models computationally tractable. My broader goal is to turn advances in optimization into practical tools for better decision-making across AI, finance, and operations.
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

  {% assign working_papers = site.data.working_papers.papers %}
  {% if working_papers and working_papers.size > 0 %}
    <div class="working-papers">
      <h3 class="working-papers__heading">Working papers</h3>

      <div class="research-list">
        {% for paper in working_papers %}
          {% assign collaborator_count = paper.collaborators | size %}
          <article class="research-item">
            <div class="research-static">
              <span class="research-title">{{ paper.title }}</span>
              {% if collaborator_count > 0 %}
                <span class="research-meta">with {% for collaborator in paper.collaborators %}{% if forloop.first %}{{ collaborator }}{% elsif forloop.last %}{% if collaborator_count > 2 %}, {% else %} {% endif %}and {{ collaborator }}{% else %}, {{ collaborator }}{% endif %}{% endfor %}</span>
              {% endif %}
            </div>
          </article>
        {% endfor %}
      </div>
    </div>
  {% endif %}
</section>

<section id="news" class="home-section news-section" aria-labelledby="news-heading">
  <h2 id="news-heading">News</h2>

  <div class="news-panel">
    <div class="news-list">
      {% for item in site.data.news %}
        <div class="news-item">
          <span class="news-date">{{ item.date }}</span>
          {{ item.text | markdownify }}
        </div>
      {% endfor %}
    </div>
  </div>
</section>

<section id="teaching" class="home-section teaching-section" aria-labelledby="teaching-heading">
  <h2 id="teaching-heading">Teaching</h2>

  {% for group in site.data.teaching %}
    <div class="teaching-group">
      <div class="teaching-group__header">
        <h3>{{ group.institution }}</h3>
        <span>{{ group.role }}</span>
      </div>
      <ul class="course-list">
        {% for course in group.courses %}
          <li class="course-item">
            <span class="course-main">
              <span class="course-name">{{ course.name }}</span>
              {% if course.url %}
                <a class="course-arrow" href="{{ course.url }}" aria-label="Open the {{ course.name }} course page">&#8599;</a>
              {% endif %}
            </span>
            {% if course.term %}<span class="course-term">{{ course.term }}</span>{% endif %}
          </li>
        {% endfor %}
      </ul>
    </div>
  {% endfor %}
</section>

<section id="service" class="home-section service-section" aria-labelledby="service-heading">
  <h2 id="service-heading">Service</h2>
  <h3>Journal Reviewing</h3>

  {% if site.data.service.journals and site.data.service.journals.size > 0 %}
    <ul class="service-list">
      {% for journal in site.data.service.journals %}
        <li class="service-item">
          <span class="service-name">{{ journal.name }}</span>
          {% if journal.url %}<a class="course-arrow" href="{{ journal.url }}" aria-label="Open the {{ journal.name }} website">&#8599;</a>{% endif %}
        </li>
      {% endfor %}
    </ul>
  {% endif %}
</section>
