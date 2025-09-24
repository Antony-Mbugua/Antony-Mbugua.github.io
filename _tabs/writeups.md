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
        <img src="/assets/images/default-writeup.png" alt="Default image">
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
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 20px;
  margin-top: 30px;
}

.writeup-card {
  display: flex;
  flex-direction: column; /* image on top, text below */
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 12px;
  overflow: hidden; /* keeps image inside card */
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
  height: 180px; /* fixed banner-style height */
  overflow: hidden;
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* fills without distortion */
}

.card-content {
  padding: 15px;
  text-align: left;
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

