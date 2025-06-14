---
layout: home
title: "CYBERSECURITY SPECIALIST"
permalink: /
author_profile: true
excerpt: "SECURING DIGITAL FRONTIERS THROUGH OFFENSIVE & DEFENSIVE STRATEGIES"
feature_row:
  - title: "CTF & PRACTICALS"
    excerpt: "TryHackMe, Hack The Box, and hands-on labs"
    url: "/writeups/"
    btn_class: "btn--primary"
    icon: "fas fa-flag"

  - title: "THREAT ANALYSIS"
    excerpt: "Basic reconnaissance, enumeration & reporting"
    url: "/tags/#threatintel"
    btn_class: "btn--info"
    icon: "fas fa-search"

  - title: "SECURITY PROJECTS"
    excerpt: "Personal & academic tools with secure design"
    url: "/projects/"
    btn_class: "btn--success"
    icon: "fas fa-terminal"

---

<style>
:root {
  --primary-color: #00bfa6;
  --dark-bg: #0e0e0e;
  --light-text: #e0e0e0;
}

@import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Orbitron:wght@700&family=Rajdhani:wght@500&display=swap');

.page__hero--overlay .page__title {
  font-family: 'Orbitron', sans-serif;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  color: var(--primary-color);
  text-shadow: 0 0 12px var(--primary-color);
}

.page__content p, .page__content li {
  font-family: 'Rajdhani', sans-serif;
  font-size: 1.05em;
  color: var(--light-text);
}

.cyber-heading {
  font-family: 'Orbitron', sans-serif;
  color: var(--primary-color);
  margin-top: 2.5rem;
  border-left: 4px solid var(--primary-color);
  padding-left: 1rem;
}

.credential-badges, .platform-badges {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
}

.credential-badge, .platform-badge {
  background: var(--dark-bg);
  border: 1px solid var(--primary-color);
  border-radius: 8px;
  padding: 1rem;
  text-align: center;
  transition: transform 0.3s;
}

.credential-badge:hover, .platform-badge:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 191, 166, 0.3);
}

.platform-badge a, .credential-badge a {
  font-family: 'Share Tech Mono', monospace;
  color: var(--primary-color);
  text-decoration: none;
}

.credential-badge h3 {
  margin-bottom: 0.5rem;
  color: var(--primary-color);
}

blockquote {
  border-left: 4px solid var(--primary-color);
  background: rgba(0, 191, 166, 0.1);
  padding: 1.5rem;
  font-family: 'Share Tech Mono', monospace;
  color: var(--light-text);
  margin: 2rem 0;
}
</style>

<div>
  <p>Hi, I’m <strong>Antony Mbugua Githinji</strong>, a cybersecurity enthusiast pursuing a BSc in Applied Computing at KCA University and currently interning at <strong>THE RED USERS</strong>.</p>

  <div class="feature__wrapper">
    {% include feature_row %}
  </div>

  <h2 class="cyber-heading"><i class="fas fa-code-branch"></i> SPECIALIZATIONS</h2>
  <ul>
    <li><i class="fas fa-shield-alt"></i> Ethical Hacking & Penetration Testing</li>
    <li><i class="fas fa-cloud"></i> Network & Cloud Security Architecture</li>
    <li><i class="fas fa-bug"></i> Incident Response & Digital Forensics</li>
    <li><i class="fas fa-search"></i> SIEM Solutions & Threat Intelligence</li>
  </ul>

  <h2 class="cyber-heading"><i class="fas fa-trophy"></i> CERTIFICATIONS & BADGES</h2>
  <div class="credential-badges">
    <div class="credential-badge">
      <h3>Cyber Shujaa Scholar</h3>
      <p>Cloud & Network Security</p>
      <a href="https://cybershujaa.co.ke" target="_blank">Verify</a>
    </div>
    <div class="credential-badge">
      <h3>(ISC)2</h3>
      <p>CC Cybersecurity</p>
      <a href="https://www.netacad.com" target="_blank">Verify</a>
    </div>
    <div class="credential-badge">
      <h3>Credly Certifications</h3>
      <p>All verified badges</p>
      <a href="https://www.credly.com/users/antonymbugua742.9c238788/badges" target="_blank">View</a>
    </div>
  </div>

  <h2 class="cyber-heading"><i class="fas fa-laptop-code"></i> TRAINING PLATFORMS</h2>
  <div class="platform-badges">
    <div class="platform-badge">
      <a href="https://app.hackthebox.com/profile/kiregi742" target="_blank">
        <i class="fas fa-terminal"></i> Hack The Box
      </a>
    </div>
    <div class="platform-badge">
      <a href="https://tryhackme.com/p/incog742" target="_blank">
        <i class="fas fa-user-secret"></i> TryHackMe
      </a>
    </div>
    <div class="platform-badge">
      <a href="https://letsdefend.io" target="_blank">
        <i class="fas fa-shield-virus"></i> LetsDefend
      </a>
    </div>
    <div class="platform-badge">
      <a href="https://www.eccouncil.org" target="_blank">
        <i class="fas fa-certificate"></i> EC-Council
      </a>
    </div>
  </div>

  <blockquote>
    "In cybersecurity, we don't just defend systems — we protect the trust placed in digital infrastructure."
    <footer>- Antony Mbugua Githinji</footer>
  </blockquote>
</div>
