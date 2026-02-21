---
layout: default
title: Home
---

> Em defesa da identidade, da ética e da soberania científica latino-americana.

---
<style>
  /* Ajuste para fonte acadêmica e discreta */
  body { font-size: 15px; line-height: 1.6; color: #333; }
  h2 { font-size: 1.3em !important; font-weight: bold; border-bottom: 1px solid #eee; padding-bottom: 5px; }
  h4 { font-size: 1.1em !important; margin-bottom: 5px; color: #0056b3; }
  .tag-container { font-size: 12px; color: #666; margin-bottom: 10px; }
  .resumo-preview { font-size: 14px; color: #444; }
  table { width: 100%; font-size: 14px; margin-bottom: 30px; }
</style>

## 🔍 Navegação por Eixos Temáticos

| **Por Território** | **Por Idioma** | **Por Categoria** |
| :--- | :--- | :--- |
| [Mapeamento Chile](/territorio-chile) | [Língua Espanhola](/idioma-espanhol) | [Instrumentos DEA](/categoria-dea) |
| [Mapeamento Colômbia](/territorio-colombia) | [Língua Portuguesa](/idioma-portugues) | [Formação (LAL)](/categoria-lal) |
| [Mapeamento Brasil](/territorio-brasil) | [Língua Inglesa](/idioma-ingles) | [Acessibilidade](/categoria-acessibilidade) |

---

## 🆕 Adições Recentes ao Acervo
*Últimos registros mapeados na nossa base de dados:*

{% for post in site.posts limit:5 %}
#### [{{ post.title }}]({{ post.url }})
<div class="tag-container">
  **Tags:** {% if post.tags %}{{ post.tags | join: ", " }}{% else %}*(Sem tags vinculadas)*{% endif %}
</div>
<div class="resumo-preview">
  {{ post.resumo_original | strip_html | truncatewords: 25 }}
</div>

---
{% endfor %}

[Ver todos os registros →](/arquivo)
