---
title: "News"
layout: gridlay
sitemap: false
permalink: /allnews.html
---

## News

<div class="section-card" markdown="0">
  <div class="news-timeline">
    {% for article in site.data.news %}
      <div class="news-item">
        <span class="news-date">{{ article.date }}</span><br><br>
        <span class="news-headline">{{ article.headline }} <a href="{{ article.link_url }}">{{ article.link_text }}</a> {{ article.headlines }}</span>
      </div>
    {% endfor %}
  </div>
</div>