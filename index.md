---
layout: home
title: "CYBERSECURITY SPECIALIST"
permalink: /
author_profile: true
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

@import url('https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Orbitron:wght@700&family=Rajdhani:wght@500&display=swap');

.page__hero--overlay .page__title {
  font-family: 'Orbitron', sans-serif;
  text-transform: uppercase;
  letter-spacing: 0.2em;
  text-shadow: 0 0 10px var(--cyber-teal);
  animation: pulse 2s infinite alternate;
}

@keyframes pulse {
  from { text-shadow: 0 0 5px var(--cyber-teal); }
  to { text-shadow: 0 0 15px var(--cyber-teal), 0 0 30px rgba(0, 255, 204, 0.7); }
}

.page__content p, .page__content li {
  font-family: 'Rajdhani', sans-serif;
  font-size: 1.05em;
}

.cyber-heading {
  font-family: 'Orbitron', sans-serif;
  color: var(--cyber-teal);
  margin-top: 2rem;
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
  padding: 10px 15px;
  font-family: 'Share Tech Mono', monospace;
  transition: all 0.3s;
}

.platform-badge:hover {
  background: rgba(0, 255, 65, 0.1);
  transform: translateY(-3px);
}

.platform-badge a {
  color: var(--matrix-green);
  text-decoration: none;
}

.credential-badges {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
}

.credential-badge {
  border: 1px solid var(--cyber-teal);
  padding: 1rem;
  border-radius: 5px;
  font-family: 'Share Tech Mono', monospace;
  transition: transform 0.3s;
}

.credential-badge:hover {
  transform: translateY(-5px);
  box-shadow: 0 5px 15px rgba(0, 255, 204, 0.3);
}

blockquote {
  border-left: 4px solid var(--cyber-purple);
  background: rgba(110, 0, 255, 0.1);
  padding: 1em;
  margin: 2em 0;
  font-family: 'Share Tech Mono', monospace;
}
</style>

<div>
  <p>Hi, I’m <strong>Antony Mbugua Githinji</strong>, a cybersecurity enthusiast pursuing a BSc in Applied Computing at KCA University and currently interning at <strong>THE RED USERS</strong>.</p>

  <div class="feature__wrapper">
    {% include feature_row %}
  </div>

  <h2 class="cyber-heading"><i class="fas fa-code-branch"></i> SPECIALIZATIONS</h2>
  <ul>
    <li>🔐 Ethical Hacking & Penetration Testing</li>
    <li>☁️ Network & Cloud Security Architecture</li>
    <li>🧬 Incident Response & Digital Forensics</li>
    <li>🧠 SIEM Solutions & Threat Intelligence</li>
  </ul>

  <h2 class="cyber-heading"><i class="fas fa-trophy"></i> CERTIFICATIONS & BADGES</h2>
  <div class="credential-badges">
    <div class="credential-badge">
      <h3>Cyber Shujaa Scholar</h3>
      <p>Cloud & Network Security</p>
      <a href="https://cybershujaa.co.ke" target="_blank">Verify</a>
    </div>
    <div class="credential-badge">
      <h3>Cisco CyberOps</h3>
      <p>Security Fundamentals</p>
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
        Hack The Box @kiregi742
      </a>
    </div>
    <div class="platform-badge">
      <a href="https://tryhackme.com/p/incog742" target="_blank">
        TryHackMe @incog742
      </a>
    </div>
    <div class="platform-badge">
      <a href="https://letsdefend.io" target="_blank">
        LetsDefend
      </a>
    </div>
    <div class="platform-badge">
      <a href="https://www.eccouncil.org" target="_blank">
        EC-Council
      </a>
    </div>
  </div>

  <blockquote>
    "In cybersecurity, we don't just defend systems - we protect the trust placed in digital infrastructure."
    <footer>- Antony Mbugua Githinji</footer>
  </blockquote>
</div>
