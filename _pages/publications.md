---
title: "Publications"
layout: gridlay
sitemap: false
permalink: /publications/
---

## Publications

<div class="section-card" id="pubList">
<p class="talk-intro">
  <i class="fa-solid fa-hand-point-right"></i>
  Click on a publication to read the full paper
</p>
<input type="text" class="pub-search" id="pubSearch" placeholder="Filter by title, author, or year...">

<div class="pub-filters">
  <button type="button" class="pub-filter-btn active" data-pub-filter="all">All</button>
  <button type="button" class="pub-filter-btn" data-pub-filter="preprint">Preprints</button>
  <button type="button" class="pub-filter-btn" data-pub-filter="articles">Journal Articles</button>
  <button type="button" class="pub-filter-btn" data-pub-filter="proceedings">Conference Proceedings</button>
</div>

{% include publication-cards.html %}
</div>

<script>
document.addEventListener('DOMContentLoaded', function () {
  const pubFilterButtons =
    document.querySelectorAll('[data-pub-filter]');

  const pubCards =
    document.querySelectorAll('[data-pub-category]');

  const pubSearch =
    document.getElementById('pubSearch');

  let activeCategory = 'all';
  let activeQuery = '';

  function renumberVisibleCards() {
    const visibleCards = Array.from(pubCards).filter(function (card) {
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
  }

  function updatePublications() {
    pubCards.forEach(function (card) {
      const cardCategory = (
        card.getAttribute('data-pub-category') || ''
      ).toLowerCase().trim();

      const cardText = card.textContent.toLowerCase();

      const matchesCategory =
        activeCategory === 'all' ||
        cardCategory === activeCategory;

      const matchesSearch =
        activeQuery === '' ||
        cardText.includes(activeQuery);

      card.style.display =
        matchesCategory && matchesSearch ? '' : 'none';
    });

    pubFilterButtons.forEach(function (button) {
      const buttonCategory = (
        button.getAttribute('data-pub-filter') || ''
      ).toLowerCase().trim();

      button.classList.toggle(
        'active',
        buttonCategory === activeCategory
      );
    });

    renumberVisibleCards();
  }

  pubFilterButtons.forEach(function (button) {
    button.addEventListener('click', function () {
      activeCategory = (
        this.getAttribute('data-pub-filter') || 'all'
      ).toLowerCase().trim();

      updatePublications();
    });
  });

  if (pubSearch) {
    pubSearch.addEventListener('input', function () {
      activeQuery = this.value.toLowerCase().trim();
      updatePublications();
    });
  }

 // Highlight your name and publication years.
document.querySelectorAll('.pub-meta').forEach(function (element) {
  element.innerHTML = element.innerHTML
    .replace(
      /D'Agostini M/g,
      '<strong class="pub-name">$&</strong>'
    )
    .replace(
      /\b(?:19|20)\d{2}\b/g,
      '<strong class="pub-year">$&</strong>'
    );
});

document.querySelectorAll('.pub-venue').forEach(function (element) {
  element.innerHTML = element.innerHTML
    .replace(
      /D'Agostini M/g,
      '<strong class="pub-name">$&</strong>'
    )
    .replace(
      /\b(?:19|20)\d{2}\b/g,
      '<strong class="pub-year">$&</strong>'
    );
});

  // Initial filtering and numbering.
  updatePublications();
});
</script>