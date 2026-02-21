---
layout: default
title: "ALALA - Início"
---

<style>
  /* Fontes menores e acadêmicas */
  body { font-size: 14px; line-height: 1.6; }
  h2 { font-size: 1.3em !important; border-bottom: 1px solid #eee; padding-bottom: 5px; }
  h4 { font-size: 1.1em !important; margin-bottom: 2px; color: #0056b3; }
  .tag-container { font-size: 12px; color: #666; margin-bottom: 10px; }
  
  /* Barra de Pesquisa */
  #search-input {
    width: 100%;
    padding: 10px;
    font-size: 15px;
    border: 1px solid #ccc;
    border-radius: 4px;
    margin-bottom: 20px;
  }
</style>

<div id="search-container">
  <input type="text" id="search-input" placeholder="Pesquisar por título, tag, autor ou país...">
  <ul id="results-container"></ul>
</div>

| **Por Território** | **Por Idioma** | **Por Categoria** |
| :--- | :--- | :--- |
| [Mapeamento Chile](/territorio-chile) | [Língua Espanhola](/idioma-espanhol) | [Instrumentos DEA](/categoria-dea) |
| [Mapeamento Colômbia](/territorio-colombia) | [Língua Portuguesa](/idioma-portugues) | [Formação (LAL)](/categoria-lal) |
| [Mapeamento Brasil](/territorio-brasil) | [Língua Inglesa](/idioma-ingles) | [Acessibilidade](/categoria-acessibilidade) |

---

## 🆕 Adições Recentes ao Acervo

{% for post in site.posts limit:5 %}
#### [{{ post.title }}]({{ post.url }})
<div class="tag-container">
<b>Tags:</b> {{ post.tags | join: ", " }}
</div>
{{ post.resumo_original | strip_html | truncatewords: 25 }}

---
{% endfor %}

<script src="/assets/js/simple-jekyll-search.min.js"></script>
<script>
  window.simpleJekyllSearch = new SimpleJekyllSearch({
    searchInput: document.getElementById('search-input'),
    resultsContainer: document.getElementById('results-container'),
    json: '/search.json'
  })
</script>
