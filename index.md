---
layout: default
title: Home
---

> Em defesa da identidade, da ética e da soberania científica latino-americana.

<div class="busca-alala" style="margin: 30px 0 20px 0;">
  <input type="text" id="search-input" placeholder="Pesquisar por país, língua ou exame..." style="width: 100%; padding: 12px; border-radius: 4px; border: 1px solid #ccc; box-sizing: border-box;">
  <ul id="results-container" style="list-style: none; padding: 0; margin: 0; border: none;"></ul>
</div>

<script src="https://unpkg.com/simple-jekyll-search@latest/dest/simple-jekyll-search.min.js"></script>

<script>
  window.simpleJekyllSearch = new SimpleJekyllSearch({
    searchInput: document.getElementById('search-input'),
    resultsContainer: document.getElementById('results-container'),
    json: '{{ site.baseurl }}/search.json',
    searchResultTemplate: '<li style="border-bottom: 1px solid #eee; padding: 10px 0;"><a href="{url}"><strong>{title}</strong></a><br><small>{summary}</small></li>',
    noResultsText: 'Nenhum resultado encontrado.',
    limit: 10,
    fuzzy: false
  })
</script>

### 🌎 Navegação por Eixos
Utilize os atalhos abaixo para explorar o acervo por categorias específicas:

| **Por Território** | **Por Idioma** | **Por Categoria** |
| :--- | :--- | :--- |
| [Mapeamento Chile]({{ '/tag.html?tag=chile' | relative_url }}) | [Língua Espanhola]({{ '/tag.html?tag=espanhol' | relative_url }}) | [Instrumentos DEA]({{ '/tag.html?tag=dea' | relative_url }}) |
| [Mapeamento Colômbia]({{ '/tag.html?tag=colombia' | relative_url }}) | [Língua Portuguesa]({{ '/tag.html?tag=portugues' | relative_url }}) | [Formação (LAL)]({{ '/tag.html?tag=lal' | relative_url }}) |
| [Mapeamento Brasil]({{ '/tag.html?tag=brasil' | relative_url }}) | [Língua Inglesa]({{ '/tag.html?tag=ingles' | relative_url }}) | [Acessibilidade]({{ '/tag.html?tag=acessibilidade' | relative_url }}) |

### 🆕 Adições Recentes ao Acervo
Confira os últimos registros mapeados na nossa base de dados:

{% for post in site.posts limit:5 %}
**[{{ post.title }}]**({{ post.url }})
<div class="tag-box">**Tags:** {{ post.tags | join: ", " }}</div>

{{ post.resumo_original | strip_html | truncatewords: 30 }}

---
{% endfor %}

[Ver todos os registros →](/arquivo)
---
