---
layout: archive
title: "Students"
permalink: /students/
author_profile: true
---

<style>
  .student-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1em;
    margin-bottom: 1em;
  }

  .student-card {
    text-align: center;
    margin-bottom: 2em;
  }

  .student-card img {
    width: 125px;
    height: 125px;
    border-radius: 50%;
    object-fit: cover;
}
</style>

**What I look for in students?**
- Motivation to do science
- Willing to conduct challenging experiments

## Current

<div class="student-grid">
{% for student in site.data.students.current %}
  <div class="student-card">
    <img src="/images/students/{{ student.photo }}" alt="{{ student.name }}">
    <h3>{{ student.name }}</h3>
    <p>{{ student.description }}</p>
  </div>
{% endfor %}
</div>

## Graduated
<div class="student-grid">
{% assign graduates = site.data.students.graduates | sort: 'year' | reverse %}
{% for student in graduates %}
  <div class="student-card">
    <img src="/images/students/{{ student.photo }}" alt="{{ student.name }}">
    <h3>{{ student.name }} ({{ student.year }})</h3>
    {{ student.current }}
  </div>
{% endfor %}
</div>

