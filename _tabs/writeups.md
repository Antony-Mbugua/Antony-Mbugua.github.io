---
# the default layout is 'page'
icon: fas fa-pen-fancy
order: 3
---

# 🔐 Writeups  

<div class="grid-container">
{% assign writeups = site.posts | where_exp:"p","p.categories contains 'writeup'" %}
{% for post in writeups %}
  <div class="card">
    <a href="{{ post.url | relative_url }}">
      <img src="{{ post.image }}" alt="{{ post.title }}">
      <h3>{{ post.title }}</h3>
    </a>
  </div>
{% endfor %}
</div>

<style>
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 1.2rem;
}
.card {
  background: var(--card-bg);
  border-radius: 12px;
  padding: 1rem;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
  text-align: center;
  transition: transform 0.2s ease;
}
.card:hover { transform: scale(1.03); }
.card img {
  width: 100%;
  height: 160px;
  object-fit: cover;
  border-radius: 8px;
  margin-bottom: .5rem;
}
</style>
