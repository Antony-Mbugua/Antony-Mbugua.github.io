---
layout: page
title: Projects
icon: fas fa-project-diagram
order: 5
---

# 🚀 Projects  

Below are some of the major systems I have developed. These appear *before* the auto-generated project cards to ensure the most important projects are always visible.

---

## ⭐ Featured Projects  

### 🔹 All Over Logistics – Transport Management System  
**Website:** [alloverlogistics.com](https://alloverlogistics.com)  
A production-ready TMS built for a U.S.–based carrier. Includes load creation, document uploads, OCR (Tesseract.js), driver app sync, expenses, invoices, secure authentication, and complete workflow automation.  
**Tech:** React, Laravel/Node (varied versions), MySQL, Tailwind, Hostinger Cloud  

---

### 🔹 277 Logistics – Transport Management System  
**Website:** [277logistics.com](https://277logistics.com)  
A customized TMS built for another mid-sized trucking company. Includes dispatcher dashboard, broker credit checks, automated invoice creation, and a streamlined operational workflow.  
**Tech:** React, MySQL, Node/Laravel, Tailwind  

---

### 🔹 Pairing System – Automatic Runs & Pair Generator  
**Website:** [tech-realm.top](https://tech-realm.top)  
A smart pairing system that automatically generates daily/weekly pairs or runs for groups, teams, or organizations. Includes admin controls and a clean UI.  
**Tech:** PHP / Laravel, MySQL, JavaScript, Tailwind  

---

# 📁 Additional Project Posts  

<div class="projects-grid">
  {% assign projects = site.posts | where_exp:"p","p.categories contains 'project'" | sort: 'date' | reverse %}
  {% if projects.size > 0 %}
    {% for post in projects %}
      <a href="{{ post.url | relative_url }}" class="project-card">
        <div class="project-image" style="background-image: url({% if post.image %}{{ post.image | relative_url }}{% else %}/assets/images/default-project.png{% endif %});">
          <div class="project-title-overlay">
            <h3>{{ post.title }}</h3>
          </div>
        </div>
        <div class="project-content">
          <p>{{ post.excerpt | strip_html | truncate: 80 }}</p>
        </div>
      </a>
    {% endfor %}
  {% else %}
    <p>No project posts yet. Stay tuned!</p>
  {% endif %}
</div>

<style>
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 20px;
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
  transition: transform 0.2s, box-shadow 0.2s;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
}

.project-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 12px rgba(0,0,0,0.15);
}

.project-image {
  width: 100%;
  height: 180px;
  background-size: cover;
  background-position: center;
  position: relative;
  display: flex;
  align-items: flex-end;
}

.project-title-overlay {
  background: rgba(0, 0, 0, 0.55);
  width: 100%;
  padding: 8px 12px;
}

.project-title-overlay h3 {
  margin: 0;
  font-size: 1.2em;
  color: #fff;
}

.project-content {
  padding: 15px;
  text-align: left;
}

.project-content p {
  margin: 0;
  color: #666;
  font-size: 0.9em;
  line-height: 1.4;
}
</style>
