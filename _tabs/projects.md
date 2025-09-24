---
layout: page
title: Projects
icon: fas fa-project-diagram
order: 5
---


<div class="cards-grid">
  {% for project in site.projects %}
    <div class="card">
      {% if project.image %}
        <div class="card-image">
          <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
        </div>
      {% endif %}
      <div class="card-content">
        <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
        <p>{{ project.excerpt | strip_html | truncate: 120 }}</p>
      </div>
    </div>
  {% endfor %}
</div>

<style>
.cards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 1.5rem;
}
.card {
  border: 1px solid var(--border-color);
  border-radius: 12px;
  overflow: hidden;
  background: var(--bg);
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}
.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 16px rgba(0,0,0,0.15);
}
.card-image img {
  width: 100%;
  height: 160px;
  object-fit: cover;
}
.card-content {
  padding: 1rem;
}
.card-content h3 {
  margin-top: 0;
  font-size: 1.1rem;
}
</style>
