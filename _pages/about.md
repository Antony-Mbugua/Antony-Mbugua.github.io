---
title: "About"
permalink: /about/
layout: single
author_profile: true
header:
  overlay_image: /assets/images/cyber-bg.jpg
  overlay_filter: rgba(0, 0, 0, 0.7)
  actions:
    - label: "View My Projects"
      url: /projects/
    - label: "Contact Me"
      url: /contact/
excerpt: "Information Security Specialist | Ethical Hacker | Secure Systems Developer"
profile:
  editable: true # Only shows edit controls when logged in via GitHub
---

{% include profile-image-editor.html %}

<div class="about-container">
  <!-- Rest of your existing content remains exactly the same -->
  <section class="intro">
    [...]
  </section>
  
  [... all other sections ...]
</div>

<style>
/* Add this to your existing CSS */
.profile-image-container {
  position: relative;
  width: 200px;
  margin: 0 auto 2rem;
  text-align: center;
}

.profile-image {
  border-radius: 50%;
  border: 3px solid #2a7ae2;
  width: 100%;
  height: auto;
  cursor: zoom-in;
  transition: all 0.3s;
}

.profile-image:hover {
  transform: scale(1.05);
  box-shadow: 0 0 15px rgba(42, 122, 226, 0.5);
}

.editor-tools {
  display: none;
  margin-top: 1rem;
}

{% if site.github.owner_name == site.author.name %}
  .profile-image-container:hover .editor-tools {
    display: block;
  }
{% endif %}

/* Rest of your existing CSS remains */
</style>

{% if site.profile.editable %}
<script>
// Only loads for you when logged in
document.addEventListener('DOMContentLoaded', function() {
  const imageUpload = document.getElementById('image-upload');
  const profileImg = document.getElementById('profile-image');
  
  imageUpload.addEventListener('change', function(e) {
    if (e.target.files && e.target.files[0]) {
      const reader = new FileReader();
      
      reader.onload = function(event) {
        profileImg.src = event.target.result;
        
        // Initialize CropperJS
        const cropper = new Cropper(profileImg, {
          aspectRatio: 1,
          viewMode: 1,
          autoCropArea: 0.8,
          responsive: true
        });
        
        document.getElementById('save-btn').addEventListener('click', function() {
          const croppedImage = cropper.getCroppedCanvas().toDataURL('image/jpeg');
          // In production: Upload to GitHub via API
          console.log('Image ready to save:', croppedImage); 
        });
      };
      
      reader.readAsDataURL(e.target.files[0]);
    }
  });
});
{% endif %}
