---
layout: home
title: "CYBERSECURITY SPECIALIST"
permalink: /
author_profile: true
## header:
  ## overlay_image: /assets/images/cyber-matrix-bg.jpg
  ## overlay_filter: rgba(0, 0, 0, 0.85)
  ## overlay_filter: "linear-gradient(rgba(10, 30, 60, 0.9), rgba(0, 200, 100, 0.3))"
 ## actions:
  ##  - label: "<i class='fas fa-terminal'></i> EXPLORE MY WORK"
  ##    url: "/projects/"
  ##    class: "btn--glow"
  ##  - label: "<i class='fas fa-shield-alt'></i> CONTACT ME"
  ##    url: "/contact/"
     ## class: "btn--danger"
excerpt: "SECURING DIGITAL FRONTIERS THROUGH OFFENSIVE & DEFENSIVE STRATEGIES"
feature_row:
  - title: "PENETRATION TESTING"
    excerpt: "Ethical hacking & vulnerability assessment"
    url: "/tags/#pentesting"
    btn_class: "btn--primary"
    icon: "fas fa-user-secret"
  - title: "THREAT RESEARCH"
    excerpt: "Malware analysis & threat intelligence"
    url: "/tags/#threatintel"
    btn_class: "btn--info"
    icon: "fas fa-bug"
  - title: "SECURE DEVELOPMENT"
    excerpt: "Building resilient systems"
    url: "/tags/#devsecops"
    btn_class: "btn--success"
    icon: "fas fa-lock"
---

<style>
:root {
  --cyber-teal: #00ffcc;
  --cyber-purple: #6e00ff;
  --matrix-green: #00ff41;
}

/* Cyberpunk font faces */
@import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Orbitron:wght@400;700&family=Rajdhani:wght@500;700&display=swap');

.page__hero--overlay .page__title {
  font-family: 'Orbitron', sans-serif;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.2em;
  text-shadow: 0 0 10px var(--cyber-teal), 0 0 20px rgba(0, 255, 204, 0.5);
  animation: pulse 2s infinite alternate;
}

@keyframes pulse {
  from { text-shadow: 0 0 5px var(--cyber-teal); }
  to { text-shadow: 0 0 15px var(--cyber-teal), 0 0 30px rgba(0, 255, 204, 0.7); }
}

.btn--glow {
  animation: btn-glow 2s infinite alternate;
  border: 1px solid var(--cyber-teal);
  font-family: 'Share Tech Mono', monospace;
}

@keyframes btn-glow {
  0% { box-shadow: 0 0 5px var(--cyber-teal); }
  100% { box-shadow: 0 0 15px var(--cyber-teal), 0 0 30px rgba(0, 255, 204, 0.5); }
}

.btn--danger {
  background-color: #ff003c;
  border-color: #ff003c;
  font-family: 'Share Tech Mono', monospace;
}

/* Cyberpunk content styling */
.page__content p, .page__content li {
  font-family: 'Rajdhani', sans-serif;
  font-weight: 500;
  font-size: 1.1em;
}

.platform-badges {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
  margin: 2em 0;
}

.platform-badge {
  background: rgba(0, 0, 0, 0.7);
  border: 1px solid var(--matrix-green);
  border-radius: 4px;
  padding: 8px 15px;
  font-family: 'Share Tech Mono', monospace;
  transition: all 0.3s;
}

.platform-badge:hover {
  background: rgba(0, 255, 65, 0.1);
  transform: translateY(-3px);
}

.platform-badge a {
  color: var(--matrix-green) !important;
  text-decoration: none;
}

blockquote {
  border-left: 4px solid var(--cyber-purple);
  font-family: 'Share Tech Mono', monospace;
  background: rgba(110, 0, 255, 0.1);
  padding: 1em;
  margin: 2em 0;
}

blockquote:before {
  content: ">";
  color: var(--cyber-purple);
  margin-right: 10px;
}

.credential-badges {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1rem;
  margin: 2rem 0;
}

.credential-badge {
  border: 1px solid var(--cyber-teal);
  padding: 1rem;
  border-radius: 5px;
  transition: transform 0.3s;
}

.credential-badge:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 255, 204, 0.3);
}

@media (max-width: 768px) {
  .page__hero--overlay .page__title {
    font-size: 1.8rem;
  }
  .credential-badges {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="cyber-content">
  <p class="cyber-text">Greetings, I'm <strong>ANTONY MBUGUA GITHINJI</strong>, a dedicated cybersecurity practitioner currently completing my BSc in Applied Computing at KCA University while interning at <strong>THE RED USERS</strong>.</p>

  <div class="feature__wrapper">
    {% include feature_row %}
  </div>

  <h2 class="cyber-heading"><i class="fas fa-code-branch"></i> SPECIALIZATIONS</h2>
  <ul class="cyber-list">
    <li><i class="fas fa-fingerprint cyber-icon"></i> Ethical Hacking & Penetration Testing</li>
    <li><i class="fas fa-network-wired cyber-icon"></i> Network & Cloud Security Architecture</li>
    <li><i class="fas fa-robot cyber-icon"></i> Incident Response & Digital Forensics</li>
    <li><i class="fas fa-chart-line cyber-icon"></i> SIEM Solutions & Threat Intelligence</li>
  </ul>

  <h2 class="cyber-heading"><i class="fas fa-trophy"></i> CERTIFICATIONS & BADGES</h2>
  <div class="credential-badges">
    <div class="credential-badge">
      <h3><i class="fas fa-certificate"></i> Cyber Shujaa Scholar</h3>
      <p>Cloud & Network Security</p>
      <a href="https://cybershujaa.co.ke" target="_blank" class="btn btn--small">Verify</a>
    </div>
    <div class="credential-badge">
      <h3><i class="fas fa-shield-alt"></i> Cisco CyberOps</h3>
      <p>Security Fundamentals</p>
      <a href="https://www.netacad.com" target="_blank" class="btn btn--small">Verify</a>
    </div>
    <div class="credential-badge">
      <h3><i class="fab fa-creative-commons"></i> Credly Badges</h3>
      <p>View all my certifications</p>
      <a href="https://www.credly.com/users/antonymbugua742.9c238788/badges" target="_blank" class="btn btn--small">View</a>
    </div>
  </div>

  <h2 class="cyber-heading"><i class="fas fa-laptop-code"></i> TRAINING PLATFORMS</h2>
  <div class="platform-badges">
    <div class="platform-badge">
      <a href="https://app.hackthebox.com/profile/kiregi742" target="_blank">
        <i class="fas fa-terminal"></i> Hack The Box @kiregi742
      </a>
    </div>
    <div class="platform-badge">
      <a href="https://tryhackme.com/p/incog742" target="_blank">
        <i class="fas fa-user-secret"></i> TryHackMe @incog742
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
    "In cybersecurity, we don't just defend systems - we protect the trust placed in digital infrastructure."
    <footer>- Antony Mbugua Githinji</footer>
  </blockquote>
</div>
