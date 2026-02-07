---
layout: page
title: Projects
icon: fas fa-project-diagram
order: 5
---

# 🚀 Projects

Hands-on labs and infrastructure builds across cybersecurity, systems, forensics, and enterprise networking.

---

## Filter by Category

<div class="project-filter">
  <button class="filter-btn active" onclick="filterProjects('all')">All</button>
  <button class="filter-btn" onclick="filterProjects('Cybersecurity')">Cybersecurity</button>
  <button class="filter-btn" onclick="filterProjects('Forensics')">Forensics</button>
  <button class="filter-btn" onclick="filterProjects('Information Security')">Information Security</button>
  <button class="filter-btn" onclick="filterProjects('Systems')">Systems</button>
  <button class="filter-btn" onclick="filterProjects('Logistics')">Logistics</button>
</div>

---

<div class="project-grid">

{% for project in site.data.projects %}
<div class="project-card"
     data-category="{{ project.category }}">

  <a href="{{ project.link }}" target="_blank">

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
function filterProjects(category) {

  const cards = document.querySelectorAll(".project-card");
  const buttons = document.querySelectorAll(".filter-btn");

  buttons.forEach(btn => btn.classList.remove("active"));
  event.target.classList.add("active");

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
  border-radius: 14px;
  overflow: hidden;
  box-shadow: var(--card-shadow);
  transition: transform 0.2s ease;
}

.project-card:hover {
  transform: translateY(-4px);
}

.project-card a {
  text-decoration: none;
  color: inherit;
}

.project-image img {
  width: 100%;
  height: 180px;
  object-fit: cover;
}

.project-content {
  padding: 16px;
}

.project-content h3 {
  margin-bottom: 8px;
}

.project-tags span {
  display: inline-block;
  background: var(--tag-bg);
  padding: 4px 8px;
  border-radius: 6px;
  margin: 4px 4px 0 0;
  font-size: 0.75rem;
}

</style>
