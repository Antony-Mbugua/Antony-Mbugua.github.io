---
layout: page
title: Projects
icon: fas fa-project-diagram
order: 5
---

# 🚀 Projects

Explore my portfolio across **Cybersecurity, Forensics, Information Security, Systems, and Logistics**.

Use the tabs below to filter projects.

---

<!-- Tabs Navigation -->

<div class="tabs" role="tablist">
  <button class="tablinks active" onclick="openCategory(event, 'All')" role="tab">All</button>
  <button class="tablinks" onclick="openCategory(event, 'Cybersecurity')" role="tab">Cybersecurity</button>
  <button class="tablinks" onclick="openCategory(event, 'Forensics')" role="tab">Forensics</button>
  <button class="tablinks" onclick="openCategory(event, 'InformationSecurity')" role="tab">Information Security</button>
  <button class="tablinks" onclick="openCategory(event, 'Systems')" role="tab">Systems</button>
  <button class="tablinks" onclick="openCategory(event, 'Logistics')" role="tab">Logistics</button>
</div>

---

{% assign categories = "All,Cybersecurity,Forensics,InformationSecurity,Systems,Logistics" | split: "," %}

{% for category in categories %}
<div id="{{ category }}" class="tabcontent {% if category == 'All' %}active{% endif %}">

  <div class="projects-grid">

    {% assign has_projects = false %}

    {% for project in site.data.projects %}
      {% assign normalized = project.category | replace: " ", "" %}

      {% if category == "All" or normalized == category %}
        {% include project-card.html project=project %}
        {% assign has_projects = true %}
      {% endif %}
    {% endfor %}

    {% unless has_projects %}
      <div class="empty-state">
        🚧 Projects coming soon in this category.
      </div>
    {% endunless %}

  </div>
</div>
{% endfor %}

---

<script>
function openCategory(evt, categoryName) {

  const tabs = document.querySelectorAll(".tabcontent");
  tabs.forEach(tab => tab.classList.remove("active"));

  const buttons = document.querySelectorAll(".tablinks");
  buttons.forEach(btn => btn.classList.remove("active"));

  const target = document.getElementById(categoryName);
  if (target) target.classList.add("active");

  evt.currentTarget.classList.add("active");
}
</script>

---

<style>

/* Tabs */

.tabs {
  overflow: hidden;
  background: #1e1e2f;
  border-radius: 12px;
  margin-bottom: 25px;
  display: flex;
  flex-wrap: wrap;
}

.tabs button {
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 12px 18px;
  color: #e0e0e0;
  font-weight: 600;
  transition: 0.3s;
}

.tabs button:hover {
  background: #2a2a40;
}

.tabs button.active {
  background: #4f8ef7;
  color: #fff;
}

/* Tab Content */

.tabcontent {
  display: none;
}

.tabcontent.active {
  display: block;
  animation: fadeIn 0.3s ease-in-out;
}

/* Grid */

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 25px;
  margin-top: 20px;
}

/* Empty State */

.empty-state {
  grid-column: 1/-1;
  padding: 30px;
  text-align: center;
  background: #1e1e2f;
  border-radius: 12px;
  color: #aaa;
  font-style: italic;
}

/* Animation */

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(5px); }
  to { opacity: 1; transform: translateY(0); }
}

</style>
