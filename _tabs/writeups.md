---
layout: page
order: 3
---

<div class="writeups-grid">
  {% for post in site.categories.Writeups %}
  <a href="{{ post.url }}" class="writeup-card">
    <div class="card-image">
      {% if post.image %}
        <img src="{{ post.image }}" alt="{{ post.title }}">
      {% else %}
        <!-- fallback avatar -->
        <img src="/assets/images/default-writeup.png" alt="Default avatar">
      {% endif %}
    </div>
    <div class="card-content">
      <h3>{{ post.title }}</h3>
      <p>{{ post.excerpt | strip_html | truncate: 80 }}</p>
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
  display: flex;
  align-items: center;
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 12px;
  padding: 15px;
  text-decoration: none;
  color: inherit;
  transition: transform 0.2s, box-shadow 0.2s;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
  gap: 15px;
}

.writeup-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 8px rgba(0,0,0,0.15);
}

.card-image {
  width: 80px;
  height: 80px;
  flex-shrink: 0;
  border-radius: 50%; /* profile look */
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #f0f0f0; /* fallback bg */
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* fill nicely */
}

.card-content {
  flex: 1;
}

.card-content h3 {
  margin: 0 0 8px 0;
  font-size: 1.1em;
  color: #333;
}

.card-content p {
  margin: 0;
  color: #666;
  font-size: 0.9em;
  line-height: 1.4;
}
</style>
