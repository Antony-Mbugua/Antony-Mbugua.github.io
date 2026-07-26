---
layout: page
title: Writeups
icon: fas fa-file-alt
order: 3
---

{% assign writeups = site.writeups | default: empty | sort: "date" | reverse %}

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
        <p>{{ post.excerpt | strip_html | truncate: 100 }}</p>
      </div>

    </a>

    {% endfor %}

  {% else %}

    <div class="no-writeups">
      <h2>No writeups yet.</h2>
      <p>Your cybersecurity writeups will appear here once you add files to the <code>_writeups</code> collection.</p>
    </div>

  {% endif %}

</div>

<style>

.writeups-grid{
  display:grid;
  grid-template-columns:repeat(auto-fill,minmax(300px,1fr));
  gap:24px;
  margin-top:2rem;
}

.writeup-card{
  display:flex;
  flex-direction:column;
  overflow:hidden;
  border-radius:12px;
  text-decoration:none;
  background:var(--card-bg,#fff);
  border:1px solid rgba(0,0,0,.08);
  transition:.25s;
}

.writeup-card:hover{
  transform:translateY(-5px);
  box-shadow:0 12px 28px rgba(0,0,0,.18);
}

.card-image{
  height:190px;
  background-size:cover;
  background-position:center;
  display:flex;
  align-items:flex-end;
}

.card-title-overlay{
  width:100%;
  padding:12px 16px;
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
  margin:0;
  color:var(--text-muted-color,#777);
  line-height:1.6;
}

.no-writeups{
  grid-column:1/-1;
  text-align:center;
  padding:60px 20px;
}

</style>