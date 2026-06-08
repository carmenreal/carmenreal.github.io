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

{% if site.data.news and site.data.news.size > 0 %}
<div class="news">
<!-- <h4 style="margin-top: 0;">News</h4> -->
### News
<div class="news-timeline" markdown="0">
{% for article in site.data.news limit:3 %}
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
