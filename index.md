---
layout: default
title: Home
---

> Em defesa da identidade, da ética e da soberania científica latino-americana.

<style>
  h2 { font-size: 1.3em !important; border-bottom: 1px solid #eee; padding-bottom: 5px; }
  h4 { font-size: 1.1em !important; margin-bottom: 5px; color: #0056b3; }
  .tag-container { font-size: 12px; color: #666; margin-bottom: 10px; }
  table { width: 100%; font-size: 14px; margin-bottom: 30px; }
</style>

## 🔍 Navegação por Eixos Temáticos

| **Por Território** | **Por Idioma** | **Por Categoria** |
| :--- | :--- | :--- |
| [Chile](/territorio-chile) | [Língua Espanhola](/idioma-espanhol) | [Instrumentos DEA](/categoria-dea) |
| [Colômbia](/territorio-colombia) | [Língua Portuguesa](/idioma-portugues) | [Formação (LAL)](/categoria-lal) |
| [Brasil](/territorio-brasil) | [Língua Inglesa](/idioma-ingles) | [Acessibilidade](/categoria-acessibilidade) |

---

## 🆕 Adições Recentes ao Acervo

{% if site.posts.size > 0 %}
  {% for post in site.posts limit:5 %}
    #### [{{ post.title }}]({{ post.url }})
    <div class="tag-container">
      **Tags:** {{ post.tags | join: ", " }}
    </div>
    {{ post.resumo_original | strip_html | truncatewords: 25 }}
    ---
  {% endfor %}
{% else %}
  <p style="color: red;">⚠️ Atenção: Nenhum post foi encontrado na pasta _posts. Verifique se os arquivos seguem o padrão de nome: ANO-MES-DIA-titulo.md</p>
{% endif %}
