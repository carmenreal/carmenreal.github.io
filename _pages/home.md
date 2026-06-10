---
title: "Home"
layout: homelay
sitemap: false
permalink: /
bibliography_style: preview
---

<h2 class="home-hero">{{ site.name }}</h2>
<p class="home-hero-sub">{{ site.title }}, {{ site.institution }}</p>

<!-- <div class="chip-container" markdown="0">
<a href="{{ site.url }}{{ site.baseurl }}/research" class="chip">Quantum Electrodynamics</a>
<a href="{{ site.url }}{{ site.baseurl }}/research" class="chip">Path Integrals</a>
<a href="{{ site.url }}{{ site.baseurl }}/research" class="chip">Superfluidity</a>
<a href="{{ site.url }}{{ site.baseurl }}/research" class="chip">Parton Model</a>
<a href="{{ site.url }}{{ site.baseurl }}/research" class="chip">Quantum Computing</a>
<a href="{{ site.url }}{{ site.baseurl }}/research" class="chip">Nanotechnology</a>
</div>

Theoretical physics is a branch of physics that focuses on the development of mathematical models and theories to understand and explain natural phenomena.
It plays a crucial role in our understanding of the fundamental laws of the universe and the fundamental particles that make up all matter.
Research in theoretical physics helps us to make predictions about how the universe works and to test these predictions through experiments.

<div class="callout callout-success" markdown="0">
<div class="callout-title"><i class="fa-solid fa-award callout-icon"></i> Nobel Prize in Physics, 1965</div>
<p>Awarded the Nobel Prize jointly with Julian Schwinger and Shin'ichiro Tomonaga for fundamental work in quantum electrodynamics, with deep-ploughing consequences for the physics of elementary particles.</p>
</div> -->

<!-- <div class="banner-frame" markdown="0">
<img src="{{ site.url }}{{ site.baseurl }}/images/banner.jpg" alt="Feynman diagrams" loading="lazy">
<div class="banner-caption">Examples of Feynman diagrams. Feynman R., <em>The theory of positrons. Phys. Rev.</em> (1949)</div>
</div> -->

<div class="section-card" style="margin-top: var(--space-6);">
### About me

I am Carmen, a Master’s student in Robotics, Graphics and Computer Vision at the University of Zaragoza. My final thesis focuses on audiovisual attention-driven audio enhancement for immersive 360° environments. I previously earned my Computer Science degree at the same university, and I am especially interested in multimodal perception, and perceptually adaptive systems.

<div class="short-pubs">

### Latest publications

{% bibliography --query @* --limit 5 %}

</div>

{% if site.data.service and site.data.service.size > 0 %}
<div class="comunity-service">
### Professional Service

{% assign reviews = site.data.service | where: "service", "reviewer" | sort: "year" | reverse %}
{% if reviews.size > 0 %}
<h4 class="service-type" style="--service-accent: {{ '#A98743' | default: '#2b7cff' }};">Reviewer</h4>
<div class="service-timeline" markdown="0">
{% assign desired = "journal|conference" | split: "|" %}

{% for t in desired %}
  {% assign items = reviews | where: "type", t %}
  {% if items.size > 0 %}
    <div class="service-item">
      <div class="service-desired">
      <span class="service-desired__badge service-desired__badge--primary" style="--color-accent: {{ '#A98743' | default: '#2b7cff' }};">{{ t | capitalize }}</span>
      <!-- <span class="service-desired__badge">{{ t | capitalize }}</span> -->
      </div>
      <div class="service-list" markdown="0">
        {% for article in items %}
          <div class="service-headline">{{ article.name }}{% if article.year %}<span class="service-year"> — {{ article.year }}</span>{% endif %}</div>
        {% endfor %}
      </div>
    </div>
  {% endif %}
{% endfor %}

{% assign types = reviews | map: "type" | uniq %}
{% for t in types %}
  {% unless desired contains t %}
    {% assign items = reviews | where: "type", t %}
    {% if items.size > 0 %}
      <div class="service-item">
        <div class="service-desired">
        <span class="service-desired__badge service-desired__badge--primary" style="--color-accent: {{ '#A98743' | default: '#2b7cff' }};">{{ t | capitalize }}</span>
        <!-- <span class="service-desired__badge">{{ t | capitalize }}</span> -->
        </div>
        <div class="service-list" markdown="0">
          {% for article in items %}
            <div class="service-headline">{{ article.name }}{% if article.year %}<span class="service-year"> — {{ article.year }}</span>{% endif %}</div>
          {% endfor %}
        </div>
      </div>
    {% endif %}
  {% endunless %}
{% endfor %}
</div>
{% endif %}

{% assign volunteer = site.data.service | where: "service", "student volunteer" | sort: "year" | reverse %}
{% if volunteer.size > 0 %}
<h4 class="service-type" style="--service-accent: {{ '#CD5D67' | default: '#2b7cff' }};">Student Volunteer</h4>
<div class="service-timeline" markdown="0">
  <div class="service-item">
    <div class="service-list" markdown="0">
      {% for article in volunteer %}
        <div class="service-headline">
        {{ article.name }}{% if article.year %}<span class="service-year"> — {{ article.year }}</span>{% endif %}
        </div>
      {% endfor %}
    </div>
  </div>
</div>

{% endif %}

</div>
{% endif %}

{% if site.data.news and site.data.news.size > 0 %}
<div class="news">
<!-- <h4 style="margin-top: 0;">News</h4> -->
### News
<div class="news-timeline" markdown="0">
{% for article in site.data.news %}
<div class="news-item">
  <div class="news-date">{{ article.date }}</div>
  <div class="news-headline">{{ article.headline }}</div>
</div>
{% endfor %}
</div>
</div>
<!-- <p style="margin-top: var(--space-4);"><a href="{{ site.url }}{{ site.baseurl }}/allnews.html">See all news &rarr;</a></p> -->
{% endif %}
</div>
