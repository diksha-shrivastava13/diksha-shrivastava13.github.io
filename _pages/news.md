---
layout: page
title: News
permalink: /news/
nav: true
nav_order: 1
---

#### What I've been up to recently 😇

{% include news.liquid %}

`A collection of my finer moments - `

<style>
.masonry-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(275px, 1fr));
  gap: 1rem;
}

.masonry-grid img {
  width: 100%;
  height: auto;
}
</style>

<div class="masonry-grid">
  {% include figure.liquid loading="eager" path="assets/img/marco_sap.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
  {% include figure.liquid loading="eager" path="assets/img/linkedin_sap.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
  {% include figure.liquid loading="eager" path="assets/img/test.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
  {% include figure.liquid loading="eager" path="assets/img/bmz_cert.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
  {% include figure.liquid loading="eager" path="assets/img/dps_fpr.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
  {% include figure.liquid loading="eager" path="assets/img/sap_cert.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
</div>


`And some awesome ones -`

<style>
  .twitter-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 1rem;
  }

  .twitter-grid iframe {
    width: 100%;
    height: auto;
    aspect-ratio: 16 / 9; /* Adjust this ratio based on Twitter's embed aspect ratio */
  }
</style>


<div class="twitter-grid">
  {% twitter https://twitter.com/Diksha1713/status/1790326914244129082 %}
  {% twitter https://twitter.com/Diksha1713/status/1826228816257380539 %}
  {% twitter https://twitter.com/Diksha1713/status/1841495118697697622 %}
  {% twitter https://twitter.com/Diksha1713/status/1821608248505692327 %}
  {% twitter https://twitter.com/Diksha1713/status/1781334449872924948 %}
  {% twitter https://twitter.com/Diksha1713/status/1791466493584294168 %}
  {% twitter https://twitter.com/Diksha1713/status/1833575023371747756 %}
  {% twitter https://twitter.com/Diksha1713/status/1783110503566381102 %}
  {% twitter https://twitter.com/Diksha1713/status/1771203046552326369 %}
  {% twitter https://twitter.com/Diksha1713/status/1768614287142953156 %}
  {% twitter https://twitter.com/Diksha1713/status/1736331388188766457 %}
  {% twitter https://twitter.com/Diksha1713/status/1692137931727630481 %}
</div>

More to be added... 🙂