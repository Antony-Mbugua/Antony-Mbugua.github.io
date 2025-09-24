---
# the default layout is 'page'
icon: fas fa-pen-fancy
order: 3
---

<div class="post-cards">
  {% assign writeups = site.posts | where_exp: "post", "post.categories contains 'Writeups'" %}
  {% for post in writeups %}
    <a href="{{ post.url | relative_url }}" class="post-card">
      <div class="post-card-image" 
           style="background-image: url('{{ post.image | default: "/assets/images/writeups-default.jpg" | relative_url }}');">
      </div>
      <div class="post-card-body">
        <h3 class="post-card-title">{{ post.title }}</h3>
        <p class="post-card-excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
      </div>
    </a>
  {% endfor %}
</div>

<style>
.post-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.2rem;
  margin-top: 1.5rem;
}
.post-card {
  display: block;
  background: var(--card-bg, #fff);
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 2px 6px rgba(0,0,0,0.12);
  text-decoration: none;
  color: inherit;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}
.post-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 6px 12px rgba(0,0,0,0.18);
}
.post-card-image {
  height: 160px;
  background-size: cover;
  background-position: center;
}
.post-card-body {
  padding: 0.8rem 1rem;
}
.post-card-title {
  font-size: 1.2rem;
  font-weight: 700;
  margin-bottom: 0.4rem;
  color: var(--heading-color, #222);
}
.post-card-excerpt {
  font-size: 0.9rem;
  line-height: 1.4;
  color: var(--text-color, #555);
}
</style>
