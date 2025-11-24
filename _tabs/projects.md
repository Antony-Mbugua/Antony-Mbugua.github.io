---
layout: page
title: Projects
icon: fas fa-project-diagram
order: 5
---

# 🚀 Projects  

Explore some of my major systems, built with real-world applications in logistics, automation, and pairing workflows. Each project includes its purpose, features, technology, and live demo link.

<div class="projects-grid">
  {% assign projects = 
    [
      {
        "title": "All Over Logistics – Transport Management System",
        "description": "A production-grade TMS built for All Over Logistics to manage shipments, drivers, dispatch, and invoices efficiently. The system improves operational efficiency and reduces manual errors by integrating real OCR, secure authentication, and automated workflows.",
        "features": [
          "Load creation & dispatch workflow",
          "OCR extraction using Tesseract.js",
          "Secure authentication with MFA & AES-256 encryption",
          "Driver mobile app synchronization",
          "Automated invoice creation",
          "Expense tracking",
          "Real-time chat with Socket.IO"
        ],
        "tech": "React, Node.js, Laravel, MySQL, Tailwind CSS, Hostinger Cloud",
        "url": "https://alloverlogistics.com",
        "image": "/assets/images/projects/aol-tms.png"
      },
      {
        "title": "277 Logistics – Transport Management System",
        "description": "A custom TMS for 277 Logistics, tailored to medium-sized carriers. Focuses on dispatch efficiency, broker management, and invoice automation, while providing a secure web dashboard for admins and dispatchers.",
        "features": [
          "Dispatcher dashboard & role-based access",
          "Broker credit check workflow",
          "Quick load creation and assignment",
          "Automated invoice PDFs",
          "Secure login and authentication",
          "Load tracking & reporting"
        ],
        "tech": "React, Laravel, Node.js, MySQL, Tailwind CSS",
        "url": "https://277logistics.com",
        "image": "/assets/images/projects/277-tms.png"
      },
      {
        "title": "Pairing System – Smart Runs & Pair Generator",
        "description": "An automated system that generates team runs and pairs dynamically, designed for organizational efficiency. Provides admins with control over schedules, validation, and exports.",
        "features": [
          "Automatic generation of pairs/runs",
          "Admin panel for managing teams and schedules",
          "Real-time validation of pair assignments",
          "Exportable results and reports",
          "Clean, intuitive UI for all users"
        ],
        "tech": "Laravel/PHP, MySQL, Tailwind CSS, JavaScript",
        "url": "https://tech-realm.top",
        "image": "/assets/images/projects/pairing-system.png"
      }
    ] 
  %}
  
  {% for project in projects %}
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
