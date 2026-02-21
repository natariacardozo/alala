---
layout: default
title: "Mapeamento: Chile"
permalink: /pais/chile
---

<style>
  h2 { font-size: 1.4em !important; border-bottom: 1px solid #eee; padding-bottom: 10px; }
  h4 { font-size: 1.1em !important; margin-bottom: 5px; }
  .post-item { margin-bottom: 30px; border-bottom: 1px solid #f0f0f0; padding-bottom: 15px; }
  .tag-meta { font-size: 12px; color: #666; margin-bottom: 8px; }
</style>

<h2 id="tag-title">Mapeamento: Chile</h2>

<div id="posts-list">
  {% for post in site.posts %}
    <div class="post-item" data-tags="{{ post.tags | join: ',' | downcase }}" style="display: none;">
      <h4><a href="{{ post.url }}">{{ post.title }}</a></h4>
      <div class="tag-meta">
        **Tags:** {{ post.tags | join: ", " }}
      </div>
      <div class="resumo-original" style="font-size: 14px;">
        {{ post.resumo_original }}
      </div>
    </div>
  {% endfor %}
</div>

<script>
  // Script ajustado para reconhecer 'chile' automaticamente nesta página
  (function() {
    const tagAlvo = "chile"; 
    const posts = document.querySelectorAll('.post-item');
    const titleEl = document.getElementById('tag-title');

    let encontrados = 0;

    posts.forEach(post => {
      // Pega as tags do atributo, limpa espaços e garante minúsculas
      const rawTags = post.getAttribute('data-tags') || "";
      const postTags = rawTags.split(',').map(t => t.trim().toLowerCase());

      if (postTags.includes(tagAlvo)) {
        post.style.display = 'block';
        encontrados++;
      } else {
        post.style.display = 'none';
      }
    });

    if (encontrados === 0) {
      titleEl.innerText = "Nenhum registro encontrado para: Chile";
    }
  })();
</script>
