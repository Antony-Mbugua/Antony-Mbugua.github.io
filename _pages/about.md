---
title: "About"
permalink: /about/
layout: single
author_profile: true
header:
  overlay_image: /assets/images/cyber-bg.jpg
  overlay_filter: rgba(0, 0, 0, 0.7)
  actions:
    - label: "📁 View Projects"
      url: /projects/
    - label: "📬 Contact Me"
      url: /contact/
excerpt: "Information Security Specialist | Ethical Hacker | Secure Systems Developer"
profile:
  editable: true
---

{% include profile-image-editor.html %}

<div class="about-container">

  <section class="intro">
    <h2>Hi, I'm Antony Mbugua 👋</h2>
    <p>
      I'm a passionate Information Security specialist with a strong background in ethical hacking, secure systems development, and digital forensics. I’m currently a finalist at KCA University, majoring in Applied Computing – Information Security and Forensics. My mission is to build and secure systems that empower businesses and protect digital infrastructures.
    </p>
  </section>

  <section class="interests">
    <h3>🔐 What I Love</h3>
    <ul>
      <li>Penetration Testing & Red Team Operations</li>
      <li>Secure Software Development (Laravel, React.js, Node.js)</li>
      <li>SIEM & Threat Intelligence Analysis</li>
      <li>Building Custom Cybersecurity Dashboards</li>
    </ul>
  </section>

  <section class="current-projects">
    <h3>🚧 Current Projects</h3>
    <ul>
      <li>🔭 <strong>Truck Management System</strong> – A full-stack logistics system for two U.S. companies.</li>
      <li>🌐 <strong>Cybersecurity Portfolio</strong> – Hosting writeups, walkthroughs, and CTFs on GitHub Pages.</li>
      <li>🏡 <strong>BnB Website</strong> – React + Laravel-powered booking platform.</li>
    </ul>
  </section>

  <section class="connect">
    <h3>📡 Let's Connect</h3>
    <p>
      I'm actively seeking cybersecurity internship opportunities and always open to collaborations or freelance tech projects. Feel free to explore my <a href="/projects/">projects</a>, read my <a href="/writeups/">writeups</a>, or <a href="/contact/">contact me</a> directly.
    </p>
  </section>

</div>

<style>
.about-container {
  max-width: 850px;
  margin: auto;
  padding: 2rem;
  font-family: 'Segoe UI', sans-serif;
  color: #ddd;
}

.about-container section {
  margin-bottom: 2.5rem;
}

.about-container h2,
.about-container h3 {
  color: #4fc3f7;
}

.about-container a {
  color: #81d4fa;
  text-decoration: underline;
}

.about-container ul {
  list-style: square;
  padding-left: 1.5rem;
}

/* Profile Image Styling */
.profile-image-container {
  position: relative;
  width: 180px;
  margin: 0 auto 2rem;
  text-align: center;
}

.profile-image {
  border-radius: 50%;
  border: 3px solid #4fc3f7;
  width: 100%;
  height: auto;
  box-shadow: 0 0 15px rgba(79, 195, 247, 0.6);
  transition: transform 0.3s ease;
}

.profile-image:hover {
  transform: scale(1.05);
}
</style>

{% if site.profile.editable %}
<script>
document.addEventListener('DOMContentLoaded', () => {
  const imageUpload = document.getElementById('image-upload');
  const profileImg = document.getElementById('profile-image');

  if (imageUpload && profileImg) {
    imageUpload.addEventListener('change', (e) => {
      const file = e.target.files[0];
      if (!file) return;

      const reader = new FileReader();
      reader.onload = (event) => {
        profileImg.src = event.target.result;

        const cropper = new Cropper(profileImg, {
          aspectRatio: 1,
          viewMode: 1,
          autoCropArea: 0.9,
        });

        document.getElementById('save-btn')?.addEventListener('click', () => {
          const croppedImage = cropper.getCroppedCanvas().toDataURL('image/jpeg');
          console.log('Cropped Image (to upload):', croppedImage);
        });
      };

      reader.readAsDataURL(file);
    });
  }
});
</script>
{% endif %}
