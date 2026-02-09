---
permalink: /
title: ""
author_profile: true
redirect_from: 
  - /welcome/
  - /welcome.html
---

<div class="welcome-header" style="text-align: center; margin-bottom: 40px;">
  <h1>Dr. Anitha Mamillapalli</h1>
  <p class="profession" style="font-size: 1.2em; color: #666;">Professor, Department of Life Sciences</p>
  <p class="lab-name" style="font-size: 1.1em; font-weight: 500;">Polyamine Research Lab</p>
</div>

## Recent publications

{% assign sorted_pubs = site.publications | sort: "date" | reverse %}
{% for post in sorted_pubs limit:3 %}
  {% include archive-single.html %}
{% endfor %}

## Gallery

<style>
    .gallery {
        display: flex;
        flex-wrap: wrap;
        gap: 10px;
        width: 40vw !important;
    }

    .gallery img {
        max-width: 200px;
        height: auto;
        object-fit: cover;
    }
</style>

<div class="gallery">
  {% for file in site.static_files %}
    {% if file.path contains 'images/gallery/' %}
      {% if file.extname == '.jpg' or file.extname == '.jpeg' or file.extname == '.png' or file.extname == '.gif' or file.extname == '.webp' %}
        <img src="{{ file.path | relative_url }}" alt="">
      {% endif %}
    {% endif %}
  {% endfor %}
</div>

