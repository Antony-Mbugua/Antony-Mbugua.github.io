---
title: "PROJECTS"
permalink: /projects/
layout: single
header:
  overlay_image: /assets/images/projects-bg.jpg
  overlay_filter: rgba(0, 0, 0, 0.85)
excerpt: "OFFENSIVE SECURITY, DEFENSIVE SECURITY & PROGRAMMING WORK"
---

<style>
.project-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
  gap: 2rem;
  margin: 3rem 0;
}

.project-card {
  background: rgba(20, 20, 40, 0.7);
  border: 1px solid var(--cyber-teal);
  border-radius: 8px;
  padding: 1.5rem;
  transition: all 0.3s;
}

.project-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 255, 204, 0.2);
}

.project-links {
  display: flex;
  gap: 1rem;
  margin-top: 1rem;
}
</style>

<div class="project-grid">

  <!-- Dev Projects -->
  <div class="project-card">
    <h3><i class="fas fa-truck"></i> TRUCK MANAGEMENT SYSTEM</h3>
    <p>Secure logistics platform for US companies with RBAC and audit logging</p>
    <div class="project-links">
      <a href="https://alloverlogistics.com" class="btn btn--small btn--success">Live Demo</a>
      <a href="#" class="btn btn--small"></a>
    </div>
        <div class="project-links">
      <a href="https://277logistics.com" class="btn btn--small btn--success">Live Demo</a>
      <a href="#" class="btn btn--small"></a>
    </div>
  </div>

  <!-- CTF -->
  <div class="project-card">
    <h3><i class="fas fa-flag"></i> CTF WRITEUPS</h3>
    <p>Detailed solutions for HackTheBox/TryHackMe machines</p>
    <div class="project-links">
      <a href="/tags/#writeups" class="btn btn--small btn--danger">View All</a>
    </div>
  </div>
</div>


