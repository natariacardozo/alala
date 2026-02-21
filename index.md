---
layout: default
title: Home
---

> Em defesa da identidade, da ética e da soberania científica latino-americana.

---
<style>
  h2 { font-size: 1.3em !important; border-bottom: 1px solid #eee; }
  h4 { font-size: 1.1em !important; margin-bottom: 2px; }
  .tags-home { font-size: 12px; color: #666; margin-bottom: 10px; }
  table { font-size: 14px; width: 100%; }
</style>

| **Por Território** | **Por Idioma** | **Por Categoria** |
| :--- | :--- | :--- |
| [Chile](/territorio-chile) | [Espanhol](/idioma-espanhol) | [Instrumentos DEA](/categoria-dea) |
| [Colômbia](/territorio-colombia) | [Português](/idioma-portugues) | [Formação (LAL)](/categoria-lal) |
| [Brasil](/territorio-brasil) | [Inglês](/idioma-ingles) | [Acessibilidade](/categoria-acessibilidade) |

---

## 🆕 Adições Recentes
{% for post in site.posts limit:10 %}
#### [{{ post.title }}]({{ post.url }})
<div class="tags-home">**Tags:** {{ post.tags | join: ", " }}</div>
{{ post.content | strip_html | truncatewords: 30 }}

---
{% endfor %}
