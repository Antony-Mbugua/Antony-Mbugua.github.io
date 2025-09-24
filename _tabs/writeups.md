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
        <img src="{{ post.image | default: '/assets/images/writeups-default.jpg' | relative_url }}" alt="{{ post.title }}">
      </div>
      <div class="post-card-body">
        <h3 class="post-card-title">{{ post.title }}</h3>
        <p class="post-card-excerpt">{{ post.excerpt | strip_html | truncate: 80 }}</p>
        <span class="post-card-link">Read More →</span>
      </div>
    </a>
  {% endfor %}
</div>

<style>
.post-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1rem;
  margin-top: 1rem;
}

.post-card {
  display: flex;
  flex-direction: column;
  background: var(--card-bg, #1e1e1e);
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 1px 4px rgba(0,0,0,0.15);
  text-decoration: none;
  color: inherit;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  max-height: 300px;
}

.post-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 4px 10px rgba(0,0,0,0.2);
}

.post-card-image img {
  width: 100%;
  height: 140px; /* compact image */
  object-fit: cover;
  display: block;
}

.post-card-body {
  padding: 0.6rem 0.9rem;
  flex-grow: 1;
}

.post-card-title {
  font-size: 1rem;
  font-weight: 700;
  margin-bottom: 0.3rem;
  color: var(--heading-color, #fff);
  line-height: 1.3;
}

.post-card-excerpt {
  font-size: 0.8rem;
  line-height: 1.3;
  color: var(--text-color, #bbb);
  margin-bottom: 0.4rem;
}

.post-card-link {
  font-size: 0.75rem;
  font-weight: 600;
  color: #4da6ff;
}
</style>
