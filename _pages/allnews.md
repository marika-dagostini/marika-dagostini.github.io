---
title: "News"
layout: gridlay
sitemap: false
permalink: /allnews.html
---

<section class="page-head page-head--banner" markdown="0">
  <div class="container">
    <h1 id="news">News</h1>
  </div>
</section>

<section class="outreach outreach--page" markdown="0">
  <div class="container section-card">
    <ol class="news-timeline dated-rows">
      {% for article in site.data.news %}
      <li class="news-item">
        <span class="news-date agate">{{ article.date }}</span>
        <p class="news-headline">{{ article.headline }} <a href="{{ article.link_url }}">{{ article.link_text }}</a> {{ article.headlines }}</p>
      </li>
      {% endfor %}
    </ol>
  </div>
</section>
