---
title: "Experience"
layout: page
permalink: /experience/
---

<style>
.news-item {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  gap: 1.5rem;
  padding: 2rem 0;
  border-bottom: 1px solid var(--border-color);
  flex-wrap: wrap;
}
.news-text {
  flex: 1 1 260px;
  min-width: 200px;
}
.news-date {
  font-style: italic;
}
.post-images {
  display: flex;
  gap: 12px;
  flex: 1 1 300px;   /* can grow to fill remaining row space */
  min-width: 220px;
}
.post-images .img-box {
  flex: 1 1 0;       /* each image shares available width equally */
  min-width: 0;
  aspect-ratio: 1 / 1;
  display: flex;
  align-items: center;
  justify-content: center;
  background: rgba(0, 0, 0, 0.03);
  border-radius: 6px;
  overflow: hidden;
}
.post-images .img-box img {
  max-width: 100%;
  max-height: 100%;
  width: auto;
  height: auto;
  object-fit: contain;
}
@media (max-width: 600px) {
  .post-images {
    flex-basis: 100%;   /* drop to its own full-width row on phones */
  }
}
</style>

# Experience

Click on each experience to learn more! 

{% if site.posts.size > 0 %}
<div class="section-card" markdown="0">
{% for post in site.posts %}
<div class="news-item">

  <div class="news-text">
    <a href="{{ post.url | relative_url }}" style="font-weight: 600;">{{ post.title }}</a>
    {% if post.blurb %}
    <p class="news-blurb" style="margin: 0.4rem 0 0; color: var(--text-color-secondary, #555);">{{ post.blurb }}</p>
    {% endif %}
  </div>

  {% if post.image1 or post.image2 or post.image3 %}
  <div class="post-images">
    {% for i in (1..3) %}
      {% assign img = nil %}
      {% if i == 1 %}{% assign img = post.image1 %}{% endif %}
      {% if i == 2 %}{% assign img = post.image2 %}{% endif %}
      {% if i == 3 %}{% assign img = post.image3 %}{% endif %}
      {% if img %}
      <div class="img-box">
        <img src="{{ img | relative_url }}" alt="{{ post.title }} image {{ i }}">
      </div>
      {% endif %}
    {% endfor %}
  </div>
  {% endif %}

</div>
{% endfor %}
</div>
{% else %}
<p class="text-muted">No blog posts yet.</p>
{% endif %}

<!-- 
---
title: "Experience"
layout: page
permalink: /experience/
---

# Experience

Click on each experience to learn more! 

{% if site.posts.size > 0 %}
<div class="section-card" markdown="0">
{% for post in site.posts %}
<div class="news-item" style="padding: 1rem 0; border-bottom: 1px solid var(--border-color);">
  <span class="news-date">{{ post.date | date: "%b %-d, %Y" }}</span><br>
  <a href="{{ post.url | relative_url }}" style="font-weight: 600;">{{ post.title }}</a>

  {% if post.image1 or post.image2 %}
  <div class="post-images" style="display: flex; gap: 12px; margin-top: 0.75rem; flex-wrap: wrap;">
    {% if post.image1 %}
    <div style="max-width: 220px; height: 140px; display: flex; align-items: center; justify-content: center; background: rgba(0, 0, 0, 0.03); border-radius: 6px; flex: 1 1 150px; overflow: hidden;">
      <img src="{{ post.image1 | relative_url }}" 
           alt="{{ post.title }} image 1" 
           style="max-width: 100%; max-height: 100%; width: auto; height: auto; object-fit: contain;">
    </div>
    {% endif %}

    {% if post.image2 %}
    <div style="max-width: 220px; height: 140px; display: flex; align-items: center; justify-content: center; background: rgba(0, 0, 0, 0.03); border-radius: 6px; flex: 1 1 150px; overflow: hidden;">
      <img src="{{ post.image2 | relative_url }}" 
           alt="{{ post.title }} image 2" 
           style="max-width: 100%; max-height: 100%; width: auto; height: auto; object-fit: contain;">
    </div>
    {% endif %}
  </div>
  {% endif %}
</div>
{% endfor %}
</div>
{% else %}
<p class="text-muted">No blog posts yet.</p>
{% endif %}
-->