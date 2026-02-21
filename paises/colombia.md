---
layout: default
title: "Mapeamento: Colômbia"
permalink: /pais/colombia
---

<style>
  h2 { font-size: 1.4em !important; border-bottom: 1px solid #eee; padding-bottom: 10px; }
  h4 { font-size: 1.1em !important; margin-bottom: 5px; color: #0056b3; }
  .post-item { margin-bottom: 30px; border-bottom: 1px solid #f0f0f0; padding-bottom: 15px; display: none; }
  .tag-meta { font-size: 12px; color: #666; margin-bottom: 8px; }
</style>

<h2 id="tag-title">Mapeamento: Colômbia</h2>

<div id="posts-list">
  {% for post in site.posts %}
    <div class="post-item" data-tags="{{ post.tags | join: ',' | downcase }}">
      <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
      <div class="tag-meta">
        **Tags:** {{ post.tags | join: ", " }}
      </div>
      <div class="resumo-original" style="font-size: 14px;">
        {{ post.resumo_original }}
      </div>
    </div>
  {% endfor %}
  <p id="empty-msg" style="display: none; color: #666; font-style: italic;">Nenhum registro encontrado para este país.</p>
</div>

<script>
  (function() {
    // Procura por "colômbia" ou "colombia" para não ter erro
    const alvos = ["colômbia", "colombia"]; 
    const posts = document.querySelectorAll('.post-item');
    const emptyMsg = document.getElementById('empty-msg');
    let encontrados = 0;

    posts.forEach(post => {
      const postTags = post.getAttribute('data-tags') || "";
      
      // Verifica se o post tem a tag da Colômbia
      const matches = alvos.some(tag => postTags.includes(tag));

      if (matches) {
        post.style.display = 'block';
        encontrados++;
      }
    });

    if (encontrados === 0) {
      emptyMsg.style.display = 'block';
    }
  })();
</script>
