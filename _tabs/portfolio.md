---
layout: portfolio
title: Portfolio
icon: fas fa-briefcase
order: 5
portfolio_url: https://heyjoseph.me
portfolio_cta: View Full Portfolio
---

## Current Project

{% assign project = site.data.current_project %}

<div class="project-card">
  <h3>{{ project.name }}</h3>
  
  <p>{{ project.description }}</p>

  <div class="tech-stack">
    {% for tech in project.tech_stack %}
      <span class="tech-badge">{{ tech }}</span>
    {% endfor %}
  </div>

  <p><strong>Status:</strong> <span class="project-status" data-status="{{ project.status | downcase }}">{{ project.status }}</span></p>
  <div class="preview-frame">
    <img
      src="{{ project.project_demo_image }}"
      alt="{{ project.project_demo_alt }}"
      class="preview-media"
    />
  </div>
</div>

## Portfolio Preview

{% if site.data.portfolio.featured_items %}
<div class="portfolio-grid">
  {% for item in site.data.portfolio.featured_items limit:3 %}
    <div class="portfolio-item">
      <h3>{{ item.title }}</h3>
      <p>{{ item.description }}</p>
      <div class="tech-stack">
        {% for tech in item.technologies %}
          <span class="tech-badge">{{ tech }}</span>
        {% endfor %}
      </div>
      {% if item.link %}
        <a href="{{ item.link }}" class="portfolio-btn" target="_blank" rel="noopener noreferrer">View Project →</a>
      {% endif %}
    </div>
  {% endfor %}
</div>
{% endif %}
