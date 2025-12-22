---
layout: page
title: Projects
icon: fas fa-project-diagram
order: 5
---

# 🚀 Projects

Explore my portfolio across **Cybersecurity, Forensics, Information Security, Systems, and Logistics**. Click tabs to filter by category.

<!-- Tabs Navigation -->
<div class="tabs">
  <button class="tablinks active" onclick="openCategory(event, 'All')">All</button>
  <button class="tablinks" onclick="openCategory(event, 'Cybersecurity')">Cybersecurity</button>
  <button class="tablinks" onclick="openCategory(event, 'Forensics')">Forensics</button>
  <button class="tablinks" onclick="openCategory(event, 'Information Security')">Information Security</button>
  <button class="tablinks" onclick="openCategory(event, 'Systems')">Systems</button>
  <button class="tablinks" onclick="openCategory(event, 'Logistics')">Logistics</button>
</div>

{% assign categories = "All,Cybersecurity,Forensics,Information Security,Systems,Logistics" | split: "," %}
{% for category in categories %}
<div id="{{ category | replace: ' ', '' }}" class="tabcontent {% if category == 'All' %}active{% endif %}">
  <div class="projects-grid">
    {% for project in site.data.projects %}
      {% if category == "All" or project.category == category %}
        {% include project-card.html project=project %}
      {% endif %}
    {% endfor %}
  </div>
</div>
{% endfor %}

<script>
function openCategory(evt, categoryName) {
  var tabcontent = document.getElementsByClassName("tabcontent");
  for (var i = 0; i < tabcontent.length; i++) {
    tabcontent[i].classList.remove("active");
  }
  var tablinks = document.getElementsByClassName("tablinks");
  for (var i = 0; i < tablinks.length; i++) {
    tablinks[i].classList.remove("active");
  }
  document.getElementById(categoryName.replace(/\s/g,'')).classList.add("active");
  evt.currentTarget.classList.add("active");
}
</script>

<style>
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
.tabs button:hover { background-color: #2a2a40; }
.tabs button.active { background-color: #4f8ef7; color: #fff; }
.tabcontent { display: none; }
.tabcontent.active { display: block; }
.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px,1fr));
  gap: 25px;
  margin-top: 20px;
}
</style>
