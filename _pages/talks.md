---
title: "Talks"
layout: gridlay
sitemap: false
permalink: /talks/
---

## Talks

<div class="section-card" id="talkList">
<p class="talk-intro">
  <i class="fa-solid fa-hand-point-right"></i>
  Click on a talk to view slides, posters, or additional material
</p>
<input type="text" class="pub-search" id="talkSearch" placeholder="Filter by title, location, topic, or year...">

<div class="talk-filters">
  <button type="button" class="talk-filter-btn active" data-talk-filter="all">All</button>
  <button type="button" class="talk-filter-btn" data-talk-filter="conference presentations">Conference Presentations</button>
  <button type="button" class="talk-filter-btn" data-talk-filter="posters">Posters</button>
  <button type="button" class="talk-filter-btn" data-talk-filter="invited talks & seminars">Seminars</button>
</div>

{% include talk-cards.html %}
</div>

<script>
document.addEventListener('DOMContentLoaded', function () {
  const talkSearch = document.getElementById('talkSearch');
  const talkFilterButtons = document.querySelectorAll('[data-talk-filter]');
  const talkCards = document.querySelectorAll('[data-talk-category]');

  let activeCategory = 'all';
  let activeQuery = '';

  function renumberVisibleCards(cards) {
  const visibleCards = Array.from(cards).filter(function (card) {
    return card.style.display !== 'none';
  });

  visibleCards.forEach(function (card, index) {
    let number = card.querySelector('.card-number');

    if (!number) {
      number = document.createElement('span');
      number.className = 'card-number';
      card.prepend(number);
    }

    number.textContent = (visibleCards.length - index) + '.';
  });
};

  function updateTalks() {
  talkCards.forEach(function (card) {
    const category = (
      card.getAttribute('data-talk-category') || ''
    ).toLowerCase().trim();

    const text = card.textContent.toLowerCase();

    const matchesCategory =
      activeCategory === 'all' ||
      category === activeCategory;

    const matchesSearch =
      activeQuery === '' ||
      text.includes(activeQuery);

    card.style.display =
      matchesCategory && matchesSearch ? '' : 'none';
  });

  talkFilterButtons.forEach(function (btn) {
    btn.classList.toggle(
      'active',
      btn.getAttribute('data-talk-filter') === activeCategory
    );
  });

  renumberVisibleCards(talkCards);
}

  if (talkSearch) {
    talkSearch.addEventListener('input', function () {
      activeQuery = this.value.toLowerCase().trim();
      updateTalks();
    });
  }

  if (talkFilterButtons.length) {
    talkFilterButtons.forEach(function (btn) {
      btn.addEventListener('click', function () {
        activeCategory = this.getAttribute('data-talk-filter').toLowerCase().trim();
        updateTalks();
      });
    });
  }

  document.querySelectorAll('.talk-meta').forEach(function (el) {
    el.innerHTML = el.innerHTML.replace(
      /D'Agostini, M/g,
      "<strong>D'Agostini, M</strong>"
    );
  });

  updateTalks();
});

// Highlight your name and publication years.
document.querySelectorAll('.talk-meta').forEach(function (element) {
  element.innerHTML = element.innerHTML
    .replace(
      /D'Agostini M/g,
      "<strong>D'Agostini M</strong>"
    )
    .replace(
      /\b(?:19|20)\d{2}\b/g,
      '<strong class="pub-year">$&</strong>'
    );
});
</script>
