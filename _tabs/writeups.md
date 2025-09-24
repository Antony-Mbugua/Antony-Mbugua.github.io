---
# the default layout is 'page'
icon: fas fa-pen-fancy
order: 3
---

<div class="grid-container">
  {%- assign writeups = site.posts | where_exp: "p",
       "p.category == 'Writeup' or p.category == 'Writeups' or p.categories contains 'Writeup' or p.categories contains 'Writeups'" -%}

  {%- if writeups.size > 0 -%}
    {%- for post in writeups -%}
      <article class="card">
        <a class="card-link" href="{{ post.url | relative_url }}">
          {% if post.image %}
            <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" class="card-img">
          {% else %}
            <img src="/assets/images/default-writeup.png" alt="default" class="card-img">
          {% endif %}
          <div class="card-body">
            <h3 class="card-title">{{ post.title }}</h3>
            <p class="card-excerpt">{{ post.excerpt | default: post.content | strip_html | truncate: 140 }}</p>
            <div class="card-meta">
              <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %d, %Y" }}</time>
              {% if post.categories and post.categories != empty %}
                <span class="card-cat">{{ post.categories | join: ", " }}</span>
              {% elsif post.category %}
                <span class="card-cat">{{ post.category }}</span>
              {% endif %}
            </div>
          </div>
        </a>
      </article>
    {%- endfor -%}
  {%- else -%}
    <p>No writeups found. Make sure your post front matter contains <code>categories: [writeup]</code> or <code>category: writeup</code>.</p>
  {%- endif -%}
</div>

<style>
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
  gap: 1.2rem;
  margin-top: 1.2rem;
}
.card {
  background: var(--card-bg, #fff);
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 3px 10px rgba(0,0,0,0.06);
  transition: transform .18s ease, box-shadow .18s ease;
}
.card:hover { transform: translateY(-6px); box-shadow: 0 8px 24px rgba(0,0,0,0.12); }
.card-link { color: inherit; text-decoration: none; display: block; }
.card-img { width: 100%; height: 150px; object-fit: cover; display:block; }
.card-body { padding: 0.9rem; }
.card-title { margin: 0 0 .5rem; font-size: 1.05rem; line-height: 1.2; }
.card-excerpt { margin: 0 0 .6rem; color: var(--muted-color, #666); font-size: 0.95rem; }
.card-meta { font-size: 0.82rem; color: var(--muted-color, #888); display:flex; gap:.6rem; align-items:center; }
.card-cat { background: rgba(0,0,0,0.05); padding:.15rem .5rem; border-radius:6px; font-weight:600; font-size:.78rem; }
</style>
