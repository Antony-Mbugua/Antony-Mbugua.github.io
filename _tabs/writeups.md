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
        <p class="post-card-excerpt">{{ post.excerpt | strip_html | truncate: 60 }}</p>
      </div>
    </a>
  {% endfor %}
</div>

<style>
.post-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); /* narrower minimum width */
  gap: 1rem;
  margin-top: 1rem;
}
.post-card {
  display: flex;
  flex-direction: column;
  background: var(--card-bg, #fff);
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 1px 4px rgba(0,0,0,0.1);
  text-decoration: none;
  color: inherit;
  transition: transform 0.15s ease, box-shadow 0.15s ease;
  max-height: 280px; /* cap card height */
}
.post-card:hover {
  transform: translateY(-3px);
  box-shadow: 0 4px 10px rgba(0,0,0,0.15);
}
.post-card-image {
  height: 120px; /* smaller image */
  background-size: cover;
  background-position: center;
}
.post-card-body {
  padding: 0.6rem 0.8rem;
  flex-grow: 1;
}
.post-card-title {
  font-size: 1rem;
  font-weight: 700;
  margin-bottom: 0.3rem;
  color: var(--heading-color, #222);
  line-height: 1.3;
}
.post-card-excerpt {
  font-size: 0.8rem;
  line-height: 1.3;
  color: var(--text-color, #555);
}
</style>
