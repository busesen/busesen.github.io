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

Hi! I am a PhD candidate in the [Risk Analytics and Optimization Lab](https://www.epfl.ch/labs/rao/) at EPFL, where I am fortunate to be advised by Prof. [Daniel Kuhn](https://people.epfl.ch/daniel.kuhn?lang=en). My research focuses on algorithms for decision-making under uncertainty that are both reliable and computable at scale. Most decisions, such as learning a control policy, pricing an option, or deploying a model, are made from limited data, unfold over time, and are brittle when tuned for the average case. My work addresses these challenges through distributionally robust methods that certify performance under distribution shift, and multilevel Monte Carlo estimators that break the exponential cost of planning over many stages.
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
      <p class="working-papers__note">Collaborators are listed alphabetically.</p>

      <div class="research-list">
        {% for paper in working_papers %}
          {% assign collaborators = paper.collaborators | sort %}
          <article class="research-item">
            <div class="research-static">
              <span class="research-title">{{ paper.title }}</span>
              {% if collaborators.size > 0 %}
                <span class="research-meta">With {{ collaborators | join: ", " }}</span>
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
