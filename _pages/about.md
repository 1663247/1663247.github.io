---
layout: academic
permalink: /
title: "Zian Wang"
description: "Zian Wang is an MS student in Computer Science at Northwestern University, working on natural language processing, large language models, and agentic systems."
redirect_from:
  - /about/
  - /about.html
---

<section id="about" aria-labelledby="about-heading" markdown="1">

# About Me
{: #about-heading }

I am a master's student in Computer Science at **Northwestern University**. My research interests broadly lie in **natural language processing and machine learning**, with a focus on large language models and agentic systems.

</section>

<section id="news" aria-labelledby="news-heading" markdown="1">

## News
{: #news-heading }

- **Sep 25, 2026** — Two papers accepted to EMNLP! Our work on [preference synthesis](https://aclanthology.org/2026.emnlp-main.1213/) was selected for an **oral presentation**, and our work on [world models for agentic RL](https://arxiv.org/abs/2510.15047) was accepted to **Findings**.

</section>

<section id="publications" aria-labelledby="publications-heading">
  <h2 id="publications-heading">Publications</h2>
  <p class="section-note">* Equal contribution</p>
  {% include research-list.html category="publication" %}
</section>

<section id="preprints" aria-labelledby="preprints-heading">
  <h2 id="preprints-heading">Preprints</h2>
  {% include research-list.html category="preprint" %}
</section>

<section id="education" aria-labelledby="education-heading">
  <h2 id="education-heading">Education</h2>
  {% for entry in site.data.profile.education %}
  <div class="record">
    <div class="record-heading"><h3>{{ entry.institution }}</h3><span class="record-date">{{ entry.dates }}</span></div>
    <p>{{ entry.degree }}</p>
  </div>
  {% endfor %}
</section>

<section id="experience" aria-labelledby="experience-heading">
  <h2 id="experience-heading">Research Experience</h2>
  {% for entry in site.data.profile.experience %}
  <div class="record">
    <div class="record-heading"><h3>{{ entry.institution }}</h3><span class="record-date">{{ entry.dates }}</span></div>
    <p>{{ entry.role }}<br><span class="muted">{{ entry.advisor }}</span></p>
  </div>
  {% endfor %}
</section>

<section id="honors" aria-labelledby="honors-heading">
  <h2 id="honors-heading">Selected Honors</h2>
  <ul class="honors-list">
    {% for honor in site.data.profile.honors %}<li>{{ honor }}</li>{% endfor %}
  </ul>
</section>
