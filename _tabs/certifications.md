---
title: Certifications
icon: fas fa-certificate
order: 5
---

# ?? Certifications

I am a Cybersecurity enthusiast and Applied Computing finalist with a passion for ethical hacking, digital forensics, and secure system design. I actively build skills through hands-on labs, certifications, and real-world projects.

---

# Badge Wallet

This page showcases your Credly badge wallet as a verified portfolio of digital credentials. The wallet includes 26 badges across cybersecurity, cloud, productivity, and secure infrastructure.

---

# Skills Wallet

The skills represented in this wallet include:
- Ethical hacking and cybersecurity fundamentals
- Network security and technical troubleshooting
- Cloud security, agent development, and Google Workspace productivity
- API security and secure application design
- Identity federation, SSO, and Active Directory security
- Critical infrastructure protection and secure system deployment

---

# Work History

Private

---

# Credly Profile

For the complete, up-to-date list of your issued badges, visit your Credly public profile:

?? **[View My Credly Profile]({{ site.data.certifications.credly_profile }})**

---

# Verified Credly Badges

<div class="certifications-grid">
  {% for cert in site.data.certifications.certifications %}
  <article class="cert-card">
    {% if cert.image_url %}
    <img class="cert-image" src="{{ cert.image_url }}" alt="{{ cert.title }} badge image" onerror="this.onerror=null; this.src='{{ '/assets/images/certification-placeholder.svg' | relative_url }}';">
    {% endif %}

    <div class="cert-card-header">
      <div>
        <h3>{{ cert.title }}</h3>
        <p class="cert-issuer">{{ cert.issuer }}</p>
      </div>
      {% if cert.verify_url %}
      <a href="{{ cert.verify_url }}" target="_blank" rel="noopener" class="cert-link">Verify</a>
      {% endif %}
    </div>

    <p>{{ cert.description }}</p>

    <div class="cert-meta">
      {% if cert.issued %}<span><strong>Issued:</strong> {{ cert.issued }}</span>{% endif %}
      {% if cert.expires %}<span><strong>Expires:</strong> {{ cert.expires }}</span>{% endif %}
    </div>
  </article>
  {% endfor %}
</div>

---

<style>
.certifications-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
  gap: 22px;
  margin-top: 20px;
}

.cert-card {
  background: var(--card-bg);
  border-radius: 20px;
  padding: 22px;
  box-shadow: var(--card-shadow);
  border: 1px solid rgba(0, 0, 0, 0.06);
  display: flex;
  flex-direction: column;
  gap: 16px;
}

.cert-image {
  width: 100%;
  border-radius: 14px;
  object-fit: cover;
  aspect-ratio: 16 / 9;
  background: #f9f9f9;
}

.cert-card-header {
  display: flex;
  justify-content: space-between;
  gap: 16px;
  align-items: flex-start;
}

.cert-link {
  display: inline-flex;
  align-items: center;
  padding: 10px 14px;
  border-radius: 999px;
  background: var(--btn-primary-bg);
  color: #fff;
  text-decoration: none;
  font-size: 0.92rem;
}

.cert-issuer {
  margin: 0;
  color: var(--text-secondary);
  font-size: 0.95rem;
}

.cert-meta {
  display: grid;
  gap: 8px;
  font-size: 0.95rem;
  color: var(--text-secondary);
}
</style>
