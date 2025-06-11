---
title: "About"
permalink: /about/
layout: single
author_profile: true
header:
  overlay_image: /assets/images/cyber-header.jpg
  overlay_filter: rgba(0, 0, 0, 0.7)
  actions:
    - label: "View My Projects"
      url: /projects/
    - label: "Contact Me"
      url: /contact/
excerpt: "Information Security Specialist | Ethical Hacker | Secure Systems Developer"
---

<div class="about-container">
  <section class="intro">
    <h2 class="section-title">👋 About Me</h2>
    <p>I'm <strong>Antony Mbugua Githinji</strong>, a final-year BSc. Applied Computing student specializing in <strong>Information Security & Forensics</strong> at KCA University (Graduating November 2025).</p>
    
    <p>Currently honing my skills as a <strong>Cybersecurity Intern</strong> at <a href="https://theredusers.com" target="_blank">The Red Users</a>, I've developed secure systems including a production-grade <strong>Trucking Management System</strong> for US logistics firms:</p>
    
    <div class="project-links">
      <a href="https://alloverlogistics.com" target="_blank" class="btn btn--primary">All Over Logistics</a>
      <a href="https://277logistics.com" target="_blank" class="btn btn--primary">277 Logistics</a>
    </div>
  </section>

  <section class="skills">
    <h2 class="section-title">🔒 Core Competencies</h2>
    
    <div class="skill-categories">
      <div class="skill-card">
        <h3><i class="fas fa-shield-alt"></i> Offensive Security</h3>
        <ul>
          <li>Penetration Testing</li>
          <li>CTF Competitions</li>
          <li>Vulnerability Assessment</li>
        </ul>
      </div>
      
      <div class="skill-card">
        <h3><i class="fas fa-network-wired"></i> Defensive Security</h3>
        <ul>
          <li>SIEM Solutions (Splunk)</li>
          <li>Network Security</li>
          <li>Incident Response</li>
        </ul>
      </div>
      
      <div class="skill-card">
        <h3><i class="fas fa-code"></i> Development</h3>
        <ul>
          <li>Secure Web Apps (Laravel/React)</li>
          <li>Cloud Security (AWS/Azure)</li>
          <li>Automation Scripts (Python/Bash)</li>
        </ul>
      </div>
    </div>
  </section>

  <section class="education">
    <h2 class="section-title">📚 Continuous Learning</h2>
    
    <div class="timeline">
      <div class="timeline-item">
        <h3>Cyber Shujaa Program</h3>
        <p>Cloud & Network Security | 2023-Present</p>
      </div>
      <div class="timeline-item">
        <h3>Hack The Box Academy</h3>
        <p>Completed 15+ modules including Advanced Web Attacks</p>
      </div>
      <div class="timeline-item">
        <h3>TryHackMe</h3>
        <p>Top 10% in Kenya | 50+ rooms completed</p>
      </div>
    </div>
  </section>

  <section class="mission">
    <h2 class="section-title">🛡️ Professional Mission</h2>
    <blockquote>
      <p>"To architect resilient systems through offensive security principles while advancing cybersecurity awareness in emerging markets."</p>
      <footer>- Antony Mbugua Githinji</footer>
    </blockquote>
    
    <div class="cta-buttons">
      <a href="/assets/docs/resume.pdf" class="btn btn--success"><i class="fas fa-file-download"></i> Download Résumé</a>
      <a href="/contact" class="btn btn--info"><i class="fas fa-envelope"></i> Get In Touch</a>
    </div>
  </section>
</div>

<style>
.about-container {
  max-width: 1200px;
  margin: 0 auto;
}

.section-title {
  border-bottom: 2px solid #2a7ae2;
  padding-bottom: 0.5em;
  margin-top: 1.5em;
}

.skill-categories {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.skill-card {
  background: rgba(42, 122, 226, 0.1);
  border-radius: 8px;
  padding: 1.5rem;
  transition: transform 0.3s;
}

.skill-card:hover {
  transform: translateY(-5px);
}

.timeline {
  border-left: 3px solid #2a7ae2;
  padding-left: 2rem;
}

.timeline-item {
  margin-bottom: 2rem;
  position: relative;
}

.timeline-item:before {
  content: "";
  position: absolute;
  left: -2.5rem;
  top: 0.5rem;
  width: 1rem;
  height: 1rem;
  border-radius: 50%;
  background: #2a7ae2;
}

.project-links {
  display: flex;
  gap: 1rem;
  margin: 1rem 0;
}

.cta-buttons {
  display: flex;
  gap: 1rem;
  margin-top: 2rem;
}

@media (max-width: 768px) {
  .skill-categories {
    grid-template-columns: 1fr;
  }
  
  .cta-buttons {
    flex-direction: column;
  }
}
</style>
