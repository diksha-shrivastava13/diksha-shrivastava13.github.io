---
layout: page
title: News
permalink: /news/
nav: true
nav_order: 1
---

#### What I've been up to recently 😇

{% include news.liquid %}

Test 1

![marco_sap.jpg](..%2Fassets%2Fimg%2Fmarco_sap.jpg)
![aim_sap.jpg](..%2Fassets%2Fimg%2Faim_sap.jpg)

Test 2

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/marco_sap.jpg" title="Marco's LinkedIn Post" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/aim_sap.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>

Test 3

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/marco_sap.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/aim_sap.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    A simple, elegant caption looks good between image rows, after each row, or doesn't have to be there at all.
</div>

Test 4
Images can be made zoomable.
Simply add `data-zoomable` to `<img>` tags that you want to make zoomable.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/marco_sap.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/10.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>

The rest of the images in this post are all zoomable, arranged into different mini-galleries.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/12.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/7.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>

Test 5

{% twitter https://twitter.com/Diksha1713/status/1833575023371747756 %}
{% twitter https://twitter.com/Diksha1713/status/1826224340695957882 %}
{% twitter https://twitter.com/Diksha1713/status/1826228816257380539 %}
{% twitter https://twitter.com/Diksha1713/status/1821608248505692327 %}
{% twitter https://twitter.com/Diksha1713/status/1791466493584294168 %}
{% twitter https://twitter.com/Diksha1713/status/1790326914244129082 %}
{% twitter https://twitter.com/Diksha1713/status/1783110503566381102 %}
{% twitter https://twitter.com/Diksha1713/status/1771203046552326369 %}
{% twitter https://twitter.com/Diksha1713/status/1768614287142953156 %}
{% twitter https://twitter.com/Diksha1713/status/1736331388188766457 %}
