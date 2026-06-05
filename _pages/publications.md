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
<input type="text" class="pub-search" id="pubSearch" placeholder="Filter by title, first author, or year...">

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
  const select = document.querySelector('[data-select]');
  const selectItems = document.querySelectorAll('[data-select-item]');
  const selectValue = document.querySelector('[data-selecct-value]');
  const filterBtns = document.querySelectorAll('[data-filter-btn]');
  const filterItems = document.querySelectorAll('[data-filter-item]');

  function applyFilter(selectedValue) {
    const value = selectedValue.toLowerCase().trim();

    filterItems.forEach(function (item) {
      const category = (item.dataset.category || '').toLowerCase().trim();
      item.classList.toggle('active', value === 'all' || value === category);
    });

    filterBtns.forEach(function (btn) {
      const btnValue = btn.textContent.toLowerCase().trim();
      btn.classList.toggle('active', btnValue === value);
    });

    if (selectValue) {
      const activeBtn = Array.from(filterBtns).find(btn => btn.classList.contains('active'));
      if (activeBtn) selectValue.textContent = activeBtn.textContent.trim();
    }
  }

  if (select) {
    select.addEventListener('click', function (e) {
      e.preventDefault();
      this.classList.toggle('active');
    });
  }

  selectItems.forEach(function (item) {
    item.addEventListener('click', function (e) {
      e.preventDefault();
      applyFilter(this.textContent);
      if (select) select.classList.remove('active');
    });
  });

  filterBtns.forEach(function (btn) {
    btn.addEventListener('click', function (e) {
      e.preventDefault();
      applyFilter(this.textContent);
    });
  });

  applyFilter('All');
});

  // ----- Publications Category Filter -----

  var pubFilterButtons = document.querySelectorAll('[data-pub-filter]');
  var pubCards = document.querySelectorAll('[data-pub-category]');

  function applyPubFilter(category) {
    pubCards.forEach(function (card) {
      var cardCategory = (card.getAttribute('data-pub-category') || '').toLowerCase();
      var matches = category === 'all' || cardCategory === category;
      card.style.display = matches ? '' : 'none';
    });

    pubFilterButtons.forEach(function (btn) {
      btn.classList.toggle('active', btn.getAttribute('data-pub-filter') === category);
    });
  }

  if (pubFilterButtons.length) {
    pubFilterButtons.forEach(function (btn) {
      btn.addEventListener('click', function () {
        applyPubFilter(this.getAttribute('data-pub-filter'));
      });
    });

    applyPubFilter('all');
  }

  // ----- Highlight my name in publications -----

document.querySelectorAll('.pub-meta').forEach(function (el) {
  el.innerHTML = el.innerHTML.replace(
    /D'Agostini, M./g,
    "<strong>D'Agostini, M.</strong>"
  );
});
</script>