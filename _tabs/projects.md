---
layout: page
title: Projects
icon: fas fa-project-diagram
order: 5
---

# 🚀 Projects  

Explore some of my major systems, built with real-world applications in logistics, automation, and pairing workflows. Each project includes its purpose, key features, technology used, and a live demo link.

<div class="projects-grid">
  {% for project in site.data.projects %}
    <a href="{{ project.url }}" target="_blank" class="project-card">
      <div class="project-image" style="background-image: url({{ project.image }});">
        <div class="project-title-overlay">
          <h3>{{ project.title }}</h3>
        </div>
      </div>
      <div class="project-content">
        <p>{{ project.description }}</p>
        <ul>
          {% for feature in project.features %}
            <li>{{ feature }}</li>
          {% endfor %}
        </ul>
        <p><strong>Tech Stack:</strong> {{ project.tech }}</p>
        <p><strong>Live Demo:</strong> <a href="{{ project.url }}" target="_blank">{{ project.url }}</a></p>
      </div>
    </a>
  {% endfor %}
</div>

<style>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 25px;
  margin-top: 30px;
}

.project-card {
  display: flex;
  flex-direction: column;
  background: var(--card-bg);
  border-radius: 12px;
  overflow: hidden;
  text-decoration: none;
  color: inherit;
  transition: transform 0.3s, box-shadow 0.3s;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
}

.project-card:hover {
  transform: translateY(-5px) scale(1.02);
  box-shadow: 0 8px 18px rgba(0,0,0,0.15);
}

.project-image {
  width: 100%;
  height: 200px;
  background-size: cover;
  background-position: center;
  position: relative;
  display: flex;
  align-items: flex-end;
  transition: transform 0.3s;
}

.project-card:hover .project-image {
  transform: scale(1.05);
}

.project-title-overlay {
  background: rgba(0, 0, 0, 0.55);
  width: 100%;
  padding: 10px 15px;
}

.project-title-overlay h3 {
  margin: 0;
  font-size: 1.3em;
  color: #fff;
}

.project-content {
  padding: 15px;
  text-align: left;
}

.project-content ul {
  margin: 5px 0;
  padding-left: 20px;
}

.project-content li {
  margin-bottom: 3px;
  font-size: 0.9em;
  color: #555;
}

.project-content p {
  margin: 5px 0;
  color: #666;
  font-size: 0.95em;
  line-height: 1.4;
}
</style>
