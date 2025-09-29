---
layout: page
icon: fas fa-file-alt
order: 3
---

<div class="writeups-grid">
  {% assign writeups = site.categories.Writeups | sort: 'date' | reverse %}
  {% for post in writeups %}
  <a href="{{ post.url }}" class="writeup-card">
    <div class="card-image" style="background-image: url({% if post.image %}{{ post.image }}{% else %}/assets/images/default-writeup.png{% endif %});">
      <div class="card-title-overlay">
        <h3>{{ post.title }}</h3>
      </div>
    </div>
    <div class="card-content">
      <p>{{ post.excerpt | strip_html | truncate: 80 }}</p>
    </div>
  </a>
  {% endfor %}
</div>

<style>
.writeups-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 20px;
  margin-top: 30px;
}

.writeup-card {
  display: flex;
  flex-direction: column;
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 12px;
  overflow: hidden;
  text-decoration: none;
  color: inherit;
  transition: transform 0.2s, box-shadow 0.2s;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
}

.writeup-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 12px rgba(0,0,0,0.15);
}

.card-image {
  width: 100%;
  height: 180px;
  background-size: cover;
  background-position: center;
  position: relative;
  display: flex;
  align-items: flex-end; /* pushes title to bottom */
}

.card-title-overlay {
  background: rgba(0, 0, 0, 0.55); /* semi-transparent overlay */
  width: 100%;
  padding: 8px 12px;
}

.card-title-overlay h3 {
  margin: 0;
  font-size: 1.2em;
  color: #fff; /* ensures title is visible */
}

.card-content {
  padding: 15px;
  text-align: left;
}

.card-content p {
  margin: 0;
  color: #666;
  font-size: 0.9em;
  line-height: 1.4;
}
</style>
