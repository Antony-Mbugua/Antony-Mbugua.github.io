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
      </div>
    </a>
  {% endfor %}
</div>

<style>
.post-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1rem;
  margin-top: 1.5rem;
}

.post-card {
  display: flex;
  flex-direction: column;
  background: var(--card-bg, #1e1e1e);
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 2px 6px rgba(0,0,0,0.15);
  text-decoration: none;
  color: inherit;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.post-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 6px 12px rgba(0,0,0,0.25);
}

.post-card-image img {
  width: 100%;
  height: 150px; /* fixed height for uniformity */
  object-fit: cover;
  display: block;
}

.post-card-body {
  padding: 0.75rem 1rem;
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.post-card-title {
  font-size: 1rem;
  font-weight: 700;
  margin-bottom: 0.4rem;
  color: var(--heading-color, #fff);
  line-height: 1.4;
}

.post-card-excerpt {
  font-size: 0.85rem;
  line-height: 1.4;
  color: var(--text-color, #aaa);
  margin-bottom: 0.4rem;
}
</style>

