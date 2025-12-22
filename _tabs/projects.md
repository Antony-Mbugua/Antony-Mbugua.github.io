---
layout: page
title: Projects
icon: fas fa-project-diagram
order: 5
---

# 🚀 Projects

Explore my portfolio across multiple domains: **Cybersecurity, Information Security, Forensics, Logistics, Systems, and Automation**. Click the tabs below to filter projects by category.

<!-- Tabs Navigation -->
<div class="tabs">
  <button class="tablinks active" onclick="openCategory(event, 'All')">All</button>
  <button class="tablinks" onclick="openCategory(event, 'Cybersecurity')">Cybersecurity</button>
  <button class="tablinks" onclick="openCategory(event, 'Forensics')">Forensics</button>
  <button class="tablinks" onclick="openCategory(event, 'InfoSec')">Information Security</button>
  <button class="tablinks" onclick="openCategory(event, 'Systems')">Systems</button>
  <button class="tablinks" onclick="openCategory(event, 'Logistics')">Logistics</button>
</div>

<!-- Projects Grid Container -->
<div id="All" class="tabcontent active">
  <div class="projects-grid">
    {% for project in site.data.projects %}
      {% include project-card.html project=project %}
    {% endfor %}
  </div>
</div>

<div id="Cybersecurity" class="tabcontent">
  <div class="projects-grid">
    {% for project in site.data.projects %}
      {% if project.category == "Cybersecurity" %}
        {% include project-card.html project=project %}
      {% endif %}
    {% endfor %}
  </div>
</div>

<div id="Forensics" class="tabcontent">
  <div class="projects-grid">
    {% for project in site.data.projects %}
      {% if project.category == "Forensics" %}
        {% include project-card.html project=project %}
      {% endif %}
    {% endfor %}
  </div>
</div>

<div id="InfoSec" class="tabcontent">
  <div class="projects-grid">
    {% for project in site.data.projects %}
      {% if project.category == "Information Security" %}
        {% include project-card.html project=project %}
      {% endif %}
    {% endfor %}
  </div>
</div>

<div id="Systems" class="tabcontent">
  <div class="projects-grid">
    {% for project in site.data.projects %}
      {% if project.category == "Systems" %}
        {% include project-card.html project=project %}
      {% endif %}
    {% endfor %}
  </div>
</div>

<div id="Logistics" class="tabcontent">
  <div class="projects-grid">
    {% for project in site.data.projects %}
      {% if project.category == "Logistics" %}
        {% include project-card.html project=project %}
      {% endif %}
    {% endfor %}
  </div>
</div>

<!-- Tab Switching Script -->
<script>
function openCategory(evt, categoryName) {
  var i, tabcontent, tablinks;
  tabcontent = document.getElementsByClassName("tabcontent");
  for (i = 0; i < tabcontent.length; i++) {
    tabcontent[i].classList.remove("active");
  }
  tablinks = document.getElementsByClassName("tablinks");
  for (i = 0; i < tablinks.length; i++) {
    tablinks[i].classList.remove("active");
  }
  document.getElementById(categoryName).classList.add("active");
  evt.currentTarget.classList.add("active");
}
</script>

<style>
/* Tabs Styling */
.tabs {
  overflow: hidden;
  background: #1e1e2f;
  margin-bottom: 25px;
  border-radius: 12px;
}

.tabs button {
  background-color: inherit;
  float: left;
  border: none;
  outline: none;
  cursor: pointer;
  padding: 12px 20px;
  transition: 0.3s;
  color: #e0e0e0;
  font-weight: 600;
}

.tabs button:hover {
  background-color: #2a2a40;
}

.tabs button.active {
  background-color: #4f8ef7;
  color: #fff;
}

/* Tab Content */
.tabcontent {
  display: none;
}

.tabcontent.active {
  display: block;
}
</style>
