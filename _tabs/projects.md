---
layout: page
title: Projects
icon: fas fa-project-diagram
order: 5
---

# 🚀 Projects

A curated selection of work spanning logistics systems, cloud and Google Workspace solutions, cybersecurity investigations, and AI-assisted automation.

---

# Filter by Category

<div class="project-filter">
  <button class="filter-btn active" onclick="filterProjects(event, 'all')">All</button>
  <button class="filter-btn" onclick="filterProjects(event, 'Cloud')">Cloud</button>
  <button class="filter-btn" onclick="filterProjects(event, 'Cybersecurity')">Cybersecurity</button>
  <button class="filter-btn" onclick="filterProjects(event, 'AI')">AI</button>
  <button class="filter-btn" onclick="filterProjects(event, 'Systems')">Systems</button>
  <button class="filter-btn" onclick="filterProjects(event, 'Logistics')">Logistics</button>
</div>

---

<div class="project-grid">

{% for project in site.data.projects %}
<div class="project-card"
     data-category="{{ project.category }}">

  <a href="{% if project.link contains 'http' %}{{ project.link }}{% else %}{{ project.link | relative_url }}{% endif %}" target="_blank" rel="noopener noreferrer">

    {% if project.image %}
    <div class="project-image">
      <img src="{{ project.image }}" alt="{{ project.title }}">
    </div>
    {% endif %}

    <div class="project-content">
      <h3>{{ project.title }}</h3>
      <p>{{ project.description }}</p>

      <div class="project-tags">
        {% for tag in project.tags %}
          <span>{{ tag }}</span>
        {% endfor %}
      </div>
    </div>

  </a>

</div>
{% endfor %}

</div>

---

<script>
function filterProjects(evt, category) {
  const cards = document.querySelectorAll(".project-card");
  const buttons = document.querySelectorAll(".filter-btn");

  buttons.forEach(btn => btn.classList.remove("active"));
  evt.currentTarget.classList.add("active");

  cards.forEach(card => {
    const cardCat = card.dataset.category;

    if (category === "all" || cardCat === category) {
      card.style.display = "block";
    } else {
      card.style.display = "none";
    }
  });
}
</script>

---

<style>

/* Filter Buttons */

.project-filter {
  margin: 20px 0;
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.filter-btn {
  padding: 6px 14px;
  border-radius: 20px;
  border: 1px solid var(--btn-border-color);
  background: transparent;
  cursor: pointer;
  font-size: 0.9rem;
  transition: 0.2s;
}

.filter-btn:hover {
  background: var(--btn-hover-bg);
}

.filter-btn.active {
  background: var(--btn-primary-bg);
  color: white;
}

/* Grid */

.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px,1fr));
  gap: 25px;
}

/* Cards */

.project-card {
  background: var(--card-bg);
  border-radius: 18px;
  overflow: hidden;
  box-shadow: var(--card-shadow);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  border: 1px solid rgba(0, 0, 0, 0.06);
}

.project-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 28px rgba(15, 23, 42, 0.12);
}

.project-card a {
  text-decoration: none;
  color: inherit;
  display: block;
}

.project-image img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  display: block;
}

.project-content {
  padding: 16px;
}

.project-content h3 {
  margin-bottom: 8px;
  font-size: 1.05rem;
}

.project-content p {
  color: var(--text-secondary);
  line-height: 1.6;
}

.project-tags span {
  display: inline-block;
  background: var(--tag-bg);
  padding: 4px 8px;
  border-radius: 999px;
  margin: 4px 4px 0 0;
  font-size: 0.75rem;
}

</style>
