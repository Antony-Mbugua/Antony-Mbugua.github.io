---
layout: page
title: Writeups
icon: fas fa-file-alt
order: 3
---

{% assign writeups = site.posts | where_exp: "post", "post.categories contains 'writeups'" | sort: "date" | reverse %}

<div class="writeups-intro">
  <p>Practical walkthroughs, investigations, and technical notes covering cybersecurity, infrastructure, and hands-on lab work.</p>
</div>

<div class="writeups-grid">

{% if writeups.size > 0 %}

  {% for post in writeups %}

  <a href="{{ post.url | relative_url }}" class="writeup-card">

    <div class="card-image"
         style="background-image: url('{% if post.image %}{{ post.image | relative_url }}{% else %}{{ '/assets/images/default-writeup.png' | relative_url }}{% endif %}');">

      <div class="card-title-overlay">
        <h3>{{ post.title }}</h3>
      </div>

    </div>

    <div class="card-content">

      {% if post.description %}
        <p>{{ post.description | truncate: 100 }}</p>
      {% else %}
        <p>{{ post.excerpt | strip_html | truncate: 100 }}</p>
      {% endif %}

      <div class="writeup-meta">
        <small>
          <i class="far fa-calendar-alt"></i>
          {{ post.date | date: "%B %d, %Y" }}
        </small>
        {% if post.categories %}
        <div class="writeup-categories">
          {% for category in post.categories %}
            {% unless category == 'Writeups' %}
            <span>{{ category }}</span>
            {% endunless %}
          {% endfor %}
        </div>
        {% endif %}
      </div>

    </div>

  </a>

  {% endfor %}

{% else %}

<div class="no-writeups">
  <i class="fas fa-folder-open fa-3x"></i>
  <h2>No writeups found</h2>
  <p>
    Add <code>categories: [writeups]</code> to your writeup posts to have them appear here.
  </p>
</div>

{% endif %}

</div>

<style>

.writeups-intro{
  margin-bottom:1.25rem;
  color:var(--text-secondary);
  font-size:1rem;
}

.writeups-grid{
  display:grid;
  grid-template-columns:repeat(auto-fill,minmax(320px,1fr));
  gap:24px;
}

.writeup-card{
  display:flex;
  flex-direction:column;
  text-decoration:none;
  color:inherit;
  overflow:hidden;
  border-radius:14px;
  background:var(--card-bg,#fff);
  border:1px solid rgba(128,128,128,.15);
  transition:all .25s ease;
}

.writeup-card:hover{
  transform:translateY(-5px);
  box-shadow:0 10px 30px rgba(0,0,0,.18);
}

.card-image{
  height:200px;
  background-size:cover;
  background-position:center;
  display:flex;
  align-items:flex-end;
}

.card-title-overlay{
  width:100%;
  padding:14px;
  background:linear-gradient(to top,rgba(0,0,0,.85),rgba(0,0,0,.15));
}

.card-title-overlay h3{
  margin:0;
  color:#fff;
  font-size:1.25rem;
}

.card-content{
  padding:18px;
}

.card-content p{
  margin-bottom:12px;
  line-height:1.6;
}

.writeup-meta{
  color:var(--text-muted-color,#888);
  font-size:.9rem;
  display:flex;
  flex-direction:column;
  gap:8px;
}

.writeup-categories{
  display:flex;
  flex-wrap:wrap;
  gap:6px;
}

.writeup-categories span{
  background:var(--tag-bg);
  color:var(--text-secondary);
  padding:4px 8px;
  border-radius:999px;
  font-size:0.78rem;
}

.no-writeups{
  grid-column:1/-1;
  text-align:center;
  padding:70px 20px;
}

.no-writeups i{
  margin-bottom:20px;
  opacity:.5;
}

.no-writeups code{
  background:rgba(127,127,127,.15);
  padding:2px 6px;
  border-radius:4px;
}

</style>