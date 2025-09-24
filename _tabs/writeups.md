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
          <img src="{{ post.image }}" alt="{{ post.title }}">
        {% else %}
          <img src="{{ '/assets/images/writeups-default.jpg' | relative_url }}" alt="{{ post.title }}">
        {% endif %}
      </div>
      <div class="post-card-body">
        <h3 class="post-card-title">{{ post.title }}</h3>
        <p class="post-card-excerpt">{{ post.excerpt | strip_html | truncate: 100 }}</p>
      </div>
    </a>
  {% endfor %}
</div>

<style>
.post-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}

.post-card {
  display: flex;
  flex-direction: column;
  background: var(--card-bg);
  border: 1px solid var(--border-color);
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 3px 10px rgba(0,0,0,0.1);
  text-decoration: none;
  color: inherit;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  height: 100%;
}

.post-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 5px 15px rgba(0,0,0,0.2);
  text-decoration: none;
  color: inherit;
}

.post-card-image {
  width: 100%;
  height: 160px;
  overflow: hidden;
  flex-shrink: 0;
}

.post-card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.post-card-body {
  padding: 1rem;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.post-card-title {
  font-size: 1.1rem;
  font-weight: 600;
  margin: 0 0 0.5rem 0;
  color: var(--heading-color);
  line-height: 1.3;
}

.post-card-excerpt {
  font-size: 0.9rem;
  line-height: 1.4;
  color: var(--text-muted-color);
  margin: 0;
  flex: 1;
}

/* Ensure images display properly */
.post-card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Responsive design */
@media (max-width: 768px) {
  .post-cards {
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1rem;
  }
}
</style>
