---
layout: page
order: 3
---

<div class="writeups-grid">
  {% for post in site.categories.Writeups %}
  <a href="{{ post.url }}" class="writeup-card">
    <div class="card-image">
      <img src="{{ post.image }}" alt="{{ post.title }}">
    </div>
    <div class="card-content">
      <h3>{{ post.title }}</h3>
      <p>{{ post.excerpt | strip_html | truncate: 100 }}</p>
    </div>
  </a>
  {% endfor %}
</div>

<style>
.writeups-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
  margin-top: 30px;
}

.writeup-card {
  display: block;
  border: 1px solid #ddd;
  border-radius: 8px;
  overflow: hidden;
  text-decoration: none;
  color: inherit;
  transition: transform 0.2s;
}

.writeup-card:hover {
  transform: translateY(-2px);
  text-decoration: none;
  color: inherit;
}

.card-image {
  width: 100%;
  height: 160px;
  overflow: hidden;
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.card-content {
  padding: 15px;
}

.card-content h3 {
  margin: 0 0 10px 0;
  font-size: 1.2em;
}

.card-content p {
  margin: 0;
  color: #666;
  font-size: 0.9em;
}
</style>
