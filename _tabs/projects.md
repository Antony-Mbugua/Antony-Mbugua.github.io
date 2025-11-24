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
    <div class="project-card">
      <div class="project-image-wrapper">
        <div class="project-image" style="background-image: url({{ project.image | relative_url }});"></div>
        <div class="overlay">
          <a href="{{ project.url }}" target="_blank" class="demo-btn">View Live Demo</a>
        </div>
      </div>
      <div class="project-content">
        <h3>{{ project.title }}</h3>
        <p>{{ project.description }}</p>
        <ul>
          {% for feature in project.features %}
            <li>{{ feature }}</li>
          {% endfor %}
        </ul>
        <p><strong>Tech Stack:</strong> {{ project.tech }}</p>
      </div>
    </div>
  {% endfor %}
</div>

<style>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 25px;
  margin-top: 30px;
}

.project-card {
  display: flex;
  flex-direction: column;
  background: var(--card-bg);
  border-radius: 12px;
  overflow: hidden;
  color: inherit;
  box-shadow: 0 3px 8px rgba(0,0,0,0.1);
  transition: transform 0.3s, box-shadow 0.3s;
}

.project-card:hover {
  transform: translateY(-5px) scale(1.02);
  box-shadow: 0 10px 20px rgba(0,0,0,0.15);
}

.project-image-wrapper {
  position: relative;
  width: 100%;
  height: 220px;
  overflow: hidden;
}

.project-image {
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  transition: transform 0.3s ease;
}

.project-card:hover .project-image {
  transform: scale(1.05);
}

.overlay {
  position: absolute;
  bottom: 10px;
  right: 10px;
}

.demo-btn {
  display: inline-block;
  padding: 6px 12px;
  background-color: var(--color-primary);
  color: #fff;
  border-radius: 6px;
  text-decoration: none;
  font-size: 0.85em;
  font-weight: bold;
  transition: background 0.2s;
}

.demo-btn:hover {
  background-color: var(--color-primary-dark);
}

.project-content {
  padding: 15px;
}

.project-content h3 {
  margin: 0 0 8px 0;
  font-size: 1.25em;
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
  font-size: 0.95em;
  color: #666;
  line-height: 1.4;
}
</style>
