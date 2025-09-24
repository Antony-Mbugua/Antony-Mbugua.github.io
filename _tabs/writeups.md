---
# the default layout is 'page'
icon: fas fa-pen-fancy
order: 3
---

<div class="cards-grid">
  {% for writeup in site.writeups %}
    <div class="card">
      {% if writeup.image %}
        <div class="card-image">
          <img src="{{ writeup.image | relative_url }}" alt="{{ writeup.title }}">
        </div>
      {% endif %}
      <div class="card-content">
        <h3><a href="{{ writeup.url | relative_url }}">{{ writeup.title }}</a></h3>
        <p>{{ writeup.excerpt | strip_html | truncate: 120 }}</p>
        {% if writeup.categories %}
          <small><strong>Category:</strong> {{ writeup.categories | join: ", " }}</small>
        {% endif %}
      </div>
    </div>
  {% endfor %}
</div>

<style>
.cards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 1.5rem;
}
.card {
  border: 1px solid var(--border-color);
  border-radius: 12px;
  overflow: hidden;
  background: var(--bg);
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}
.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 16px rgba(0,0,0,0.15);
}
.card-image img {
  width: 100%;
  height: 160px;
  object-fit: cover;
}
.card-content {
  padding: 1rem;
}
.card-content h3 {
  margin-top: 0;
  font-size: 1.1rem;
}
</style>

