---
title: "About"
layout: gridlay
sitemap: false
permalink: /about/
---

## About

<div class="section-card">
<div class="pi-card">
<img src="{{ site.url }}{{ site.baseurl }}/images/{{ site.photo }}" class="pi-photo" alt="{{ site.name }}" loading="lazy">
<div>
<h3 class="pi-name">{{ site.name }}</h3>
<p style="font-style: italic; color: var(--text-secondary);">{{ site.title }}, {{ site.institution }}</p>
<p><a class="icon-link" title="Email"><i class="fa-solid fa-envelope"></i></a><a href="mailto:{{ site.email }}"> marika.dagostini2@unibo.it</a></p>
<p><a class="icon-link" title="Address"><i class="fa-solid fa-map-pin"></i></a><a href="https://maps.app.goo.gl/DStb48BMJA9QDtacA"> Viale Quirico Filopanti 5, 40126 Bologna BO (Italy)</a></p>
<div class="pi-links">
{% if site.links.university and site.links.university != "" %}<a href="{{ site.links.university }}" class="icon-link" title="UniBO Website"><i class="ai ai-archive"></i></a>{% endif %}
{% if site.links.cv and site.links.cv != "" %}<a href="{{ site.links.cv }}" class="icon-link" title="CV"><i class="ai ai-cv"></i></a>{% endif %}
{% if site.links.google_scholar and site.links.google_scholar != "" %}<a href="{{ site.links.google_scholar }}" class="icon-link" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>{% endif %}
{% if site.links.github and site.links.github != "" %}<a href="{{ site.links.github }}" class="icon-link" title="GitHub"><i class="fa-brands fa-github"></i></a>{% endif %}
{% if site.links.researchgate and site.links.researchgate != "" %}<a href="{{ site.links.researchgate }}" class="icon-link" title="ResearchGate"><i class="ai ai-researchgate"></i></a>{% endif %}
</div>
{% if site.data.pi[0].education %}
<ul style="margin-top: var(--space-4);">
{% for education in site.data.pi[0].education %}
<li>{{ education | replace: "-","&#8211;" }}</li>
{% endfor %}
</ul>
{% endif %}
</div>
</div>
</div>

{% if site.data.grants %}
<div class="section-card">
<h3>Education</h3>
<section class="timeline">
  <ol class="timeline-list">
    {% for grant in site.data.grants %}
    <li class="timeline-item">
      <h4 class="timeline-degree">{{ grant.title }}</h4>
      <span class="timeline-date">{{ grant.period }}</span>
      <p class="timeline-place"><strong>{{ grant.institution }}</strong></p>
      {% if grant.topic %}
      <p class="timeline-text">
        {{ grant.topic_label | default: "Research Topic" }}:
        <em>{{ grant.topic }}</em>
      </p>
      {% endif %}
      {% if grant.supervisors %}
      <p class="timeline-text">
        Supervisors: {{ grant.supervisors }}
      </p>
      {% endif %}
      {% if grant.supervisor %}
      <p class="timeline-text">
        Supervisor: {{ grant.supervisor }}
      </p>
      {% endif %}
      {% if grant.co_supervisors %}
      <p class="timeline-text">
        Co-Supervisors: {{ grant.co_supervisors }}
      </p>
      {% endif %}
    </li>
    {% endfor %}
  </ol>
</section>
{% endif %}
</div>


{% if site.data.awards %}
<div class="section-card">
<h3>Experience</h3>
<section class="timeline">
  <ol class="timeline-list">
    {% for job in site.data.awards %}
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
{% endif %}

{% if site.data.funders %}
<div class="section-card">
<h4>Ongoing Collaborations </h4>
<div class="sponsor-logos" style="display: flex; flex-wrap: wrap; align-items: center; justify-content: center; gap: var(--space-6);">
{% for funder in site.data.funders %}
<a href="{{ funder.url }}" target="_blank"><img src="{{ site.url }}{{ site.baseurl }}/images/{{ funder.image }}" alt="Funder logo" style="max-height: 80px; max-width: 200px; border-radius: 0;" loading="lazy"></a>
{% endfor %}
</div>
</div>
{% endif %}
