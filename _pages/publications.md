---
title: "Publications"
layout: gridlay
sitemap: false
permalink: /publications/
---

<section class="page-head page-head--banner" markdown="0">
  <div class="container">
    <h1 id="publications">Publications</h1>
    <p class="lead talk-intro">Click on a publication to read the full paper</p>
  </div>
</section>

<section class="index-section" markdown="0">
<div class="container section-card" id="pubList">
<div class="index-tools">
<input type="text" class="pub-search" id="pubSearch" placeholder="Filter by title, author, or year" aria-label="Filter publications by title, author, or year">

<div class="pub-filters" role="group" aria-label="Publication type">
  <button type="button" class="pub-filter-btn active" data-pub-filter="all">All</button>
  <button type="button" class="pub-filter-btn" data-pub-filter="preprint">Preprints</button>
  <button type="button" class="pub-filter-btn" data-pub-filter="articles">Journal Articles</button>
  <button type="button" class="pub-filter-btn" data-pub-filter="proceedings">Conference Proceedings</button>
</div>
</div>

{% include publication-cards.html %}
</div>
</section>

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