---
layout: page
permalink: /publications/
title: publications
description: † denotes equal contribution | * denotes corresponding authorship
years: [2026,2025,2024,2023,2022,2021,2020,2019,2018,2017]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<div class="publications publications-page">

  <div class="pub-controls">
    {% include bib_search.html %}

    <div id="pub-filters" class="pub-filters">
      <div class="filter-options">
        <button class="btn btn-sm z-depth-0 active filter-all" data-filter="all">ALL</button>
        <button class="btn btn-sm z-depth-0" data-filter="selected">SELECTED</button>
        <button class="btn btn-sm z-depth-0" data-filter="topic:comp-chem">COMP-CHEM</button>
        <button class="btn btn-sm z-depth-0" data-filter="topic:ai-ml">AI/ML</button>
        <button class="btn btn-sm z-depth-0" data-filter="applied">APPLIED</button>
        <button class="btn btn-sm z-depth-0" data-filter="topic:review">REVIEW</button>
        <button class="btn btn-sm z-depth-0" data-filter="system:boride">BORIDE</button>
        <button class="btn btn-sm z-depth-0" data-filter="system:copper">COPPER</button>
        <button class="btn btn-sm z-depth-0" data-filter="system:molecules">MOLECULES</button>
        <button class="btn btn-sm z-depth-0" data-filter="system:clusters">CLUSTERS</button>
        <button class="btn btn-sm z-depth-0" data-filter="system:sac">SAC</button>
        <button class="btn btn-sm z-depth-0" data-filter="topic:restructuring">RESTRUCTURING</button>
        <button class="btn btn-sm z-depth-0" data-filter="application:electro-catal">ELECTRO-CATAL</button>
        <button class="btn btn-sm z-depth-0" data-filter="application:thermal-catal">THERMAL-CATAL</button>
        <button class="btn btn-sm z-depth-0" data-filter="application:photo-catal">PHOTO-CATAL</button>
        <button class="btn btn-sm z-depth-0" data-filter="application:battery">BATTERY</button>
        <button class="btn btn-sm z-depth-0" data-filter="application:separation">SEPARATION</button>
      </div>
    </div>
  </div>

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>

{% include publications_js.html %}
