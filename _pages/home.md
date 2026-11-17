---
title: "Home"
layout: homelay
sitemap: false
permalink: /
---

<section class="hero" markdown="0">
  <div class="container hero-grid">
    <div class="hero-text">
      <h1>{{ site.name }}</h1>
      <p class="lead">{{ site.title }}, <br> Department of Statistical Sciences "Paolo Fortunati", <br>{{ site.institution }}</p>
      <div class="actions">
        <a class="btn btn--primary" href="mailto:{{ site.email }}">Email me</a>
        {% if site.links.cv and site.links.cv != "" %}<a class="btn btn--secondary" href="{{ site.links.cv }}">Download the CV</a>{% endif %}
      </div>
    </div>
    <figure class="hero-photo">
      <a href="{{ site.url }}{{ site.baseurl }}/about" class="photo-link" aria-label="About {{ site.name }}">
        <img src="{{ site.url }}{{ site.baseurl }}/images/{{ site.photo }}" width="1678" height="1678" alt="Portrait of {{ site.name }}" fetchpriority="high">
      </a>
    </figure>
  </div>
</section>

<section class="front" markdown="0">
  <div class="container">
    <hr class="rule--double">
    <div class="front-grid">
      <div class="front-story">
        <h2 class="display-s front-head">Bayesian spatio-temporal models for environment and health</h2>
        <div class="cols">
          <p class="dropcap">I am a <strong>PhD candidate in Statistical Sciences</strong> at the <a href="https://stat.unibo.it/en">University of Bologna</a>, where I work on Bayesian spatio-temporal modelling for environmental and epidemiological studies under the supervision of <a href="https://www.unibo.it/sitoweb/massimo.ventrucci/en">Massimo Ventrucci</a> and <a href="https://www.unibo.it/sitoweb/andrea.ranzi/en">Andrea Ranzi</a>.</p>
          <p>Here, you’ll find my publications, research updates, and materials from conferences and seminars, along with a glimpse into the projects and questions I’m currently exploring.</p>
          <p><strong>I hope you enjoy looking around!</strong></p>
        </div>
      </div>
      <aside class="front-index" aria-labelledby="areas-head">
        <h3 id="areas-head">Research areas</h3>
        <ul class="topic-list">
          <li><a href="{{ site.url }}{{ site.baseurl }}/research" class="chip">Bayesian Hierarchical Models</a></li>
          <li><a href="{{ site.url }}{{ site.baseurl }}/research" class="chip">INLA</a></li>
          <li><a href="{{ site.url }}{{ site.baseurl }}/research" class="chip">Urban Studies</a></li>
          <li><a href="{{ site.url }}{{ site.baseurl }}/research" class="chip">Environmental & Occupational Epidemiology</a></li>
         <!-- <li><a href="{{ site.url }}{{ site.baseurl }}/research" class="chip">Tourism Analytics</a></li> -->
          <li><a href="{{ site.url }}{{ site.baseurl }}/research" class="chip">Geospatial Data Visualization</a></li>
        </ul>
      </aside>
    </div>
  </div>
</section>

<!---

My research explores how **climate change** and **urbanization** shape our cities and our health. Using Bayesian hierarchical models, I investigate how environmental, climatic, and socioeconomic factors interact to influence exposure, vulnerability, and health inequalities across communities.


<div class="callout callout-success" markdown="0">
<div class="callout-title"><i class="fa-solid fa-calendar callout-icon"></i> Next Talks</div>
<p><ul>
<li>June 22–25: <b>SIS-FENStatS</b>, Rome (Italy)</li>
</ul></p>
</div>

<!--- <div class="banner-frame" markdown="0">
<img src="{{ site.url }}{{ site.baseurl }}/images/banner.jpg" alt="Feltre" loading="lazy">
<div class="banner-caption"><em>Landscape of my hometown, Feltre (BL)</em></div>
</div> -->

<!--- More broadly, I see **statistics as a bridge between complex data and policymaking**, and I aim to develop methods that are both rigorous and easy to interpret. The PhD scholarship is funded by [ARPAE](https://www.arpae.it/it) within the project *[“Health and Equity Co-Benefits in Support of Plans to Respond to Climate Change in Italy”](https://climaesalute.it/)*, part of the Italian National Plan for Complementary Investments of the Ministry of Health. Alongside research, I am a **teaching tutor** for the Bayesian Inference course led by [Daniela Cocchi](https://www.unibo.it/sitoweb/daniela.cocchi/en), and I work as a **statistical consultant** for the Emilia-Romagna Region on a project investigating the socioeconomic factors associated with an increased risk of **occupational injuries**. -->
