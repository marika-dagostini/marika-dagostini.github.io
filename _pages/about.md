---
title: "About"
layout: gridlay
sitemap: false
permalink: /about/
---

<section class="page-head" markdown="0">
  <div class="container page-head-grid">
    <div class="pi-card">
      <h1 id="about">About</h1>
      <h3></h3>
      <dl class="facts">
        <div><dt>Email</dt><dd><a href="mailto:{{ site.email }}">marika.dagostini2@unibo.it</a></dd></div>
        <div><dt>Addresses</dt><dd><a href="https://maps.app.goo.gl/DStb48BMJA9QDtacA">Viale Quirico Filopanti 5, 40126 Bologna</a></dd><dt> </dt><dd><a href="https://maps.app.goo.gl/FAZNWoknU3UYqozp6">Piazzetta Teatini 10, 47921 Rimini</a></dd></div>
      </dl>
      <ul class="pi-links icon-links">
        {% if site.links.university and site.links.university != "" %}<li><a href="{{ site.links.university }}" title="UniBO Website"><i class="ai ai-archive" aria-hidden="true"></i><span class="visually-hidden">UniBO Website</span></a></li>{% endif %}
        {% if site.links.cv and site.links.cv != "" %}<li><a href="{{ site.links.cv }}" title="CV"><i class="ai ai-cv" aria-hidden="true"></i><span class="visually-hidden">CV</span></a></li>{% endif %}
        {% if site.links.google_scholar and site.links.google_scholar != "" %}<li><a href="{{ site.links.google_scholar }}" title="Google Scholar"><i class="ai ai-google-scholar" aria-hidden="true"></i><span class="visually-hidden">Google Scholar</span></a></li>{% endif %}
        {% if site.links.github and site.links.github != "" %}<li><a href="{{ site.links.github }}" title="GitHub"><i class="fa-brands fa-github" aria-hidden="true"></i><span class="visually-hidden">GitHub</span></a></li>{% endif %}
        {% if site.links.researchgate and site.links.researchgate != "" %}<li><a href="{{ site.links.researchgate }}" title="ResearchGate"><i class="ai ai-researchgate" aria-hidden="true"></i><span class="visually-hidden">ResearchGate</span></a></li>{% endif %}
      </ul>
      {% if site.data.pi[0].education %}
      <ul class="plain-list">
        {% for education in site.data.pi[0].education %}
        <li>{{ education }}</li>
        {% endfor %}
      </ul>
      {% endif %}
    </div>
    <figure class="pi-figure">
      <img src="{{ site.url }}{{ site.baseurl }}/images/{{ site.photo }}" class="pi-photo" width="1678" height="1678" alt="Portrait of {{ site.name }}">
    </figure>
  </div>
</section>

{% if site.data.grants %}
<section class="record" markdown="0">
  <div class="container record-grid">
    <h2>Education</h2>
    <ol class="timeline-list">
      {% for grant in site.data.grants %}
      <li class="timeline-item">
        <span class="timeline-date agate">{{ grant.period }}</span>
        <div>
          <h3 class="timeline-degree">{{ grant.title }}</h3>
          <p class="timeline-place">{{ grant.institution }}</p>
          {% if grant.topic %}<p class="timeline-text">{{ grant.topic_label | default: "Research Topic" }}: <em>{{ grant.topic }}</em></p>{% endif %}
          {% if grant.supervisors %}<p class="timeline-text">Supervisors: {{ grant.supervisors }}</p>{% endif %}
          {% if grant.supervisor %}<p class="timeline-text">Supervisor: {{ grant.supervisor }}</p>{% endif %}
          {% if grant.co_supervisors %}<p class="timeline-text">Co-Supervisors: {{ grant.co_supervisors }}</p>{% endif %}
          {% if grant.co_supervisor %}<p class="timeline-text">Co-Supervisor: {{ grant.co_supervisor }}</p>{% endif %}
        </div>
      </li>
      {% endfor %}
    </ol>
  </div>
</section>
{% endif %}

{% if site.data.research-fellow %}
<section class="record record--well" markdown="0">
  <div class="container record-grid">
    <h2>Experience</h2>
    <ol class="timeline-list">
      {% for research-fellow in site.data.research-fellow %}
      <li class="timeline-item">
        <span class="timeline-date agate">{{ research-fellow.period }}</span>
        <div>
          <h3 class="timeline-degree">{{ research-fellow.title }}</h3>
          <p class="timeline-place">{{ research-fellow.institution }}</p>
          {% if research-fellow.topic %}<p class="timeline-text">{{ research-fellow.topic_label | default: "Research Topic" }}: <em>{{ research-fellow.topic }}</em></p>{% endif %}
          {% if research-fellow.supervisors %}<p class="timeline-text">Supervisors: {{ research-fellow.supervisors }}</p>{% endif %}
          {% if research-fellow.supervisor %}<p class="timeline-text">Supervisor: {{ research-fellow.supervisor }}</p>{% endif %}
          {% if research-fellow.co_supervisors %}<p class="timeline-text">Co-Supervisors: {{ research-fellow.co_supervisors }}</p>{% endif %}
        </div>
      </li>
      {% endfor %}
    </ol>
  </div>
</section>
{% endif %}

<!-- {% if site.data.funders %}
<section class="collaborations" markdown="0">
  <div class="container">
    <h2>Ongoing Collaborations</h2>
    <ul class="sponsor-logos">
      {% for funder in site.data.funders %}
      <li><a href="{{ funder.url }}" target="_blank" rel="noopener"><img src="{{ site.url }}{{ site.baseurl }}/images/{{ funder.image }}" alt="Funder logo" loading="lazy"></a></li>
      {% endfor %}
    </ul>
  </div>
</section>
{% endif %}

 {% if site.data.cv %}
<div class="section-card">
<h3>Research & Work Experience</h3>
<section class="timeline">
  <ol class="timeline-list">
    {% for job in site.data.cv %}
    <li class="timeline-item">
      <h4 class="timeline-degree">{{ job.role }}</h4>
      <span class="timeline-date">{{ job.year }}</span>
      <p class="timeline-text">
        {{ job.place }}
      </p>
    </li>
    {% endfor %}
  </ol>
</section>
</div>
{% endif %}

{% if site.data.people %}
<div class="section-card">
<h3>Students and Mentoring</h3>
<ul>
{% for student in site.data.people %}
<li>{{ student.name }}, {{ student.location }} ({{ student.degree }}, {{ student.year }})</li>
{% endfor %}
</ul>
</div>
{% endif %} --->
