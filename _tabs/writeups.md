---
# the default layout is 'page'
icon: fas fa-pen-fancy
order: 3
---

# 🔍 Writeups  

I publish walkthroughs and reports from labs, real-world security challenges, and SOC-related tasks.  

---

## 🛡 Cybersecurity
{% assign posts = site.categories['cybersecurity'] %}
{% for post in posts %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}

---

## 🖥 SOC
{% assign posts = site.categories['soc'] %}
{% for post in posts %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}

---

## 📂 All Others
{% assign posts = site.categories['other'] %}
{% for post in posts %}
- [{{ post.title }}]({{ post.url }})
{% endfor %}

