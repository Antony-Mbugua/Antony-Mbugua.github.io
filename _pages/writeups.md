---
title: "Writeups"
layout: single
permalink: /writeups/
classes: wide
author_profile: true
---

## 🛠️ Cybersecurity Writeups

Welcome to my curated collection of walkthroughs and CTF reports.

---

<div class="chirpy-writeup-grid">
  {% assign writeups = site.data.feature_row.writeup_highlight %}
  {% for item in writeups %}
    <article class="chirpy-post-card">
      <a href="{{ item.url | relative_url }}">
        <div class="chirpy-thumbnail">
          <img src="{{ item.image_path | relative_url }}" alt="{{ item.alt }}">
        </div>
        <div class="chirpy-post-content">
          <h3>{{ item.title }}</h3>
          <p>{{ item.excerpt | strip_html | truncate: 140 }}</p>
        </div>
      </a>
    </article>
  {% endfor %}
</div>

<style>
.chirpy-writeup-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.chirpy-post-card {
  background: #1a1a1a;
  border: 1px solid #2a2a2a;
  border-radius: 10px;
  overflow: hidden;
  transition: all 0.3s ease;
  box-shadow: 0 2px 8px rgba(0,0,0,0.2);
}

.chirpy-post-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0,0,0,0.3);
}

.chirpy-post-card a {
  text-decoration: none;
  color: inherit;
  display: block;
  height: 100%;
}

.chirpy-thumbnail img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  display: block;
}

.chirpy-post-content {
  padding: 1rem;
}

.chirpy-post-content h3 {
  font-size: 1.2rem;
  color: #00bfff;
  margin: 0 0 0.5rem;
}

.chirpy-post-content p {
  font-size: 0.9rem;
  color: #ccc;
  margin: 0;
}
</style>
