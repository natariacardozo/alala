---
layout: default
title: "Mapeamento: México"
permalink: /pais/mexico
---

<style>
  h2 { font-size: 1.4em !important; border-bottom: 1px solid #eee; padding-bottom: 10px; }
  h4 { font-size: 1.1em !important; margin-bottom: 5px; color: #0056b3; }
  .post-item { margin-bottom: 30px; border-bottom: 1px solid #f0f0f0; padding-bottom: 15px; }
  .tag-meta { font-size: 12px; color: #666; margin-bottom: 8px; }
</style>

<h2 id="tag-title">Mapeamento: México</h2>

<div id="posts-list">
  {% for post in site.posts %}
    <div class="post-item" data-tags="{{ post.tags | join: ',' }}" style="display: none;">
      <h4><a href="{{ post.url }}">{{ post.title }}</a></h4>
      <div class="tag-meta">
        <b>Tags:</b> {{ post.tags | join: ", " }}
      </div>
      <div class="resumo-original" style="font-size: 14px;">
        {{ post.resumo_original }}
      </div>
    </div>
  {% endfor %}
</div>

<script>
  (function() {
    const tagAlvo = "méxico"; // Filtro específico para o México
    const posts = document.querySelectorAll('.post-item');
    const titleEl = document.getElementById('tag-title');
    let encontrados = 0;

    posts.forEach(post => {
      const rawTags = post.getAttribute('data-tags') || "";
      // Padroniza para comparar sem erros de capitalização ou espaços extras
      const postTags = rawTags.split(',').map(t => t.trim().toLowerCase());

      // Verifica se a tag "méxico" ou "mexico" está presente
      if (postTags.includes(tagAlvo.toLowerCase()) || postTags.includes("mexico")) {
        post.style.display = 'block';
        encontrados++;
      }
    });

    if (encontrados === 0) {
      titleEl.innerText = "Nenhum registro encontrado para: México";
    }
  })();
</script>
