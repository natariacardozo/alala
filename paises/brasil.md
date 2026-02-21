---
layout: default
title: "Mapeamento: Brasil"
permalink: /pais/brasil
---

<h2 id="tag-title">Mapeamento: Brasil</h2>

<div id="posts-list">
  {% for post in site.posts %}
    <div class="post-item" data-tags="{{ post.tags | join: ',' }}" style="display: none;">
      <h4><a href="{{ post.url }}">{{ post.title }}</a></h4>
      <div class="tag-meta">**Tags:** {{ post.tags | join: ", " }}</div>
      <div style="font-size: 14px;">{{ post.resumo_original }}</div>
    </div>
  {% endfor %}
</div>

<script>
  (function() {
    const tagAlvo = "brasil"; 
    const posts = document.querySelectorAll('.post-item');
    posts.forEach(post => {
      const rawTags = post.getAttribute('data-tags') || "";
      const postTags = rawTags.split(',').map(t => t.trim().toLowerCase());
      if (postTags.includes(tagAlvo)) { post.style.display = 'block'; }
    });
  })();
</script>
