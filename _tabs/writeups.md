---
# the default layout is 'page'
icon: fas fa-pen-fancy
order: 3
---

<div class="post-cards">
  {% assign writeups = site.posts | where_exp: "post", "post.categories contains 'Writeups'" %}
  {% for post in writeups %}
    <a href="{{ post.url | relative_url }}" class="post-card">
      <div class="post-card-image">
        {% if post.image %}
          <img src="{{ post.image | relative_url }}" alt="{{ post.title }}">
        {% else %}
          <img src="{{ '/assets/images/writeups-default.jpg' | relative_url }}" alt="{{ post.title }}">
        {% endif %}
      </div>
      <div class="post-card-body">
        <h3 class="post-card-title">{{ post.title }}</h3>
        <p class="post-card-excerpt">{{ post.excerpt | strip_html | truncate: 80 }}</p>
      </div>
    </a>
  {% endfor %}
</div>

<style>
.post-cards {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.post-card {
  display: block;
  background: var(--card-bg);
  border: 1px solid var(--border-color);
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 6px rgba(0,0,0,0.1);
  text-decoration: none;
  color: inherit;
  transition: all 0.3s ease;
  height: 100%;
}

.post-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(0,0,0,0.15);
  text-decoration: none;
  color: inherit;
}

.post-card-image {
  width: 100%;
  height: 180px;
  overflow: hidden;
}

.post-card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.post-card:hover .post-card-image img {
  transform: scale(1.05);
}

.post-card-body {
  padding: 1.25rem;
}

.post-card-title {
  font-size: 1.2rem;
  font-weight: 600;
  margin-bottom: 0.75rem;
  color: var(--heading-color);
  line-height: 1.4;
}

.post-card-excerpt {
  font-size: 0.95rem;
  line-height: 1.5;
  color: var(--text-muted-color);
  margin: 0;
}

/* Responsive design */
@media (max-width: 768px) {
  .post-cards {
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.5rem;
  }
}

@media (max-width: 480px) {
  .post-cards {
    grid-template-columns: 1fr;
    gap: 1rem;
  }
}
</style>
