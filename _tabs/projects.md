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
      <div class="project-image-wrapper">
        <div class="project-image" style="background-image: url({{ project.image }});"></div>
        <div class="overlay">
          <a href="{{ project.url }}" target="_blank" class="demo-btn">View Demo</a>
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

.project-image-wrapper {
  position: relative;
  width: 100%;
  height: 200px;
  overflow: hidden;
  border-bottom: 1px solid #eee;
}

.project-image {
  width: 100%;
  height: 100%;
  background-size: cover;
  background-position: center;
  transition: transform 0.5s ease;
}

.project-card:hover .project-image {
  transform: scale(1.1);
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.4);
  opacity: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: opacity 0.3s ease;
}

.project-card:hover .overlay {
  opacity: 1;
}

.demo-btn {
  padding: 8px 16px;
  background: #1e90ff;
  color: white;
  border-radius: 8px;
  text-decoration: none;
  font-weight: bold;
  transition: background 0.3s;
}

.demo-btn:hover {
  background: #0d6efd;
}

.project-content {
  padding: 15px;
  text-align: left;
}

.project-content h3 {
  margin: 0 0 10px 0;
  font-size: 1.3em;
  color: var(--primary-color);
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
