---
title: "Blog"
layout: page
permalink: /blog/
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