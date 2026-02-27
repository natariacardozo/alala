---
layout: default
title: "Arquivo"
permalink: /arquivo/
---

<style>
  h2 { font-size: 1.4em !important; border-bottom: 1px solid #eee; padding-bottom: 10px; }
  h4 { font-size: 1.1em !important; margin-bottom: 5px; color: #0056b3; }
  .post-item { margin-bottom: 30px; border-bottom: 1px solid #f0f0f0; padding-bottom: 15px; }
  .tag-meta { font-size: 12px; color: #666; margin-bottom: 8px; }
</style>

<h2>Arquivo Completo do Acervo</h2>
<p style="font-size: 14px; color: #555;">Todos os registros indexados no ALALA, listados da inserção mais recente para a mais antiga.</p>

<div id="posts-list">
  {% for post in site.posts %}
    <div class="post-item">
      <h4><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h4>
      <div class="tag-meta">
        <b>Tags:</b> {{ post.tags | join: ", " }}
      </div>
      <div class="resumo-original" style="font-size: 14px;">
        {{ post.resumo_original | strip_html | truncatewords: 35 }}
      </div>
    </div>
  {% endfor %}
</div>
