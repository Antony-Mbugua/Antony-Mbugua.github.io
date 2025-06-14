---
title: "Writeups"
layout: single
permalink: /writeups/
classes: wide
author_profile: true
---

## 🛠️ Cybersecurity Writeups

Welcome to my curated collection of hands-on walkthroughs from platforms like **TryHackMe**, **Hack The Box**, and **VulnHub**.

Each card includes:
- 🔍 Target Summary
- 🧰 Tools Used
- 📝 Step-by-Step Exploitation

---

<div class="writeup-grid">
  {% for post in site.writeups %}
    <div class="writeup-card">
      <a href="{{ post.url | relative_url }}">
        <img src="{{ post.image | default: '/assets/images/writeup-thumb.jpg' }}" alt="{{ post.title }}">
        <div class="writeup-content">
          <h3>{{ post.title }}</h3>
          <p>{{ post.excerpt | markdownify | strip_html | truncate: 100 }}</p>
        </div>
      </a>
    </div>
  {% endfor %}
</div>

<style>
.writeup-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}

.writeup-card {
  background: #1e1e1e;
  border-radius: 12px;
  overflow: hidden;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border: 1px solid #2a2a2a;
}

.writeup-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 18px rgba(0,0,0,0.5);
}

.writeup-card img {
  width: 100%;
  height: 160px;
  object-fit: cover;
}

.writeup-content {
  padding: 1rem;
}

.writeup-content h3 {
  margin-top: 0;
  margin-bottom: 0.5rem;
  font-size: 1.1rem;
  color: #00bfff;
}

.writeup-content p {
  font-size: 0.9rem;
  color: #ccc;
}
</style>
