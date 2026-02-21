---
layout: default
title: "ALALA - Início"
---

Em defesa da identidade, da ética e da soberania científica latino-americana.

---

<style>
  /* Estilo acadêmico, minimalista e sem cores berrantes */
  body { font-size: 14px; line-height: 1.6; color: #333; }
  h2 { font-size: 1.3em !important; border-bottom: 1px solid #eee; padding-bottom: 5px; margin-top: 25px; }
  h4 { font-size: 1.1em !important; margin-bottom: 2px; color: #0056b3; }
  .tag-container { font-size: 12px; color: #666; margin-bottom: 10px; }
  
  /* Barra de Pesquisa Neutra */
  #search-input {
    width: 100%;
    padding: 12px;
    font-size: 15px;
    border: 1px solid #ccc; /* Cinza discreto */
    border-radius: 4px;
    margin-bottom: 20px;
    outline: none;
    transition: border-color 0.2s;
  }
  
  #search-input:focus {
    border-color: #666; /* Escurece suavemente ao clicar */
    box-shadow: 0 0 5px rgba(0,0,0,0.05);
  }

  #results-container { 
    list-style: none; 
    padding: 0; 
    margin-bottom: 30px; 
  }
  #results-container li { 
    background: #fdfdfd; 
    padding: 12px; 
    border: 1px solid #eee; 
    border-radius: 4px;
    margin-bottom: 8px;
  }
</style>

<div id="search-area">
  <input type="text" id="search-input" placeholder="Pesquisar por título, país, tag ou autor...">
  <ul id="results-container"></ul>
</div>

| **Por Território** | **Por Idioma** | **Por Categoria** |
| :--- | :--- | :--- |
| [Chile](/pais/chile) | [Espanhol](/idioma/espanhol) | [Instrumentos DEA](/categoria/dea) |
| [Colômbia](/pais/colombia) | [Português](/idioma/portugues) | [Formação (LAL)](/categoria/lal) |
| [Brasil](/pais/brasil) | [Inglês](/idioma/ingles) | [Acessibilidade](/categoria/acessibilidade) |

---

## 🆕 Adições Recentes ao Acervo
*Confira os últimos registros mapeados:*

{% for post in site.posts limit:5 %}
#### [{{ post.title | escape }}]({{ post.url | relative_url }})
<div class="tag-container">
  <b>Tags:</b> {{ post.tags | join: ", " }}
</div>
{{ post.resumo_original | strip_html | truncatewords: 30 }}

---
{% endfor %}

<script>
  (function() {
    let searchData = [];
    const input = document.getElementById('search-input');
    const results = document.getElementById('results-container');

    // Busca o arquivo JSON da raiz do site
    fetch('{{ "/search.json" | relative_url }}')
      .then(response => {
        if (!response.ok) throw new Error("Erro ao carregar search.json");
        return response.json();
      })
      .then(data => { 
        searchData = data;
        console.log("ALALA: Banco de dados carregado.");
      })
      .catch(err => console.error("Erro na busca: ", err));

    input.addEventListener('input', function() {
      const query = this.value.toLowerCase().trim();
      results.innerHTML = '';

      if (query.length < 2) return;

      const filtered = searchData.filter(item => 
        (item.title || "").toLowerCase().includes(query) || 
        (item.tags || "").toLowerCase().includes(query) ||
        (item.resumo || "").toLowerCase().includes(query)
      );

      if (filtered.length === 0) {
        results.innerHTML = '<li style="color:#666; list-style:none;">Nenhum registro encontrado.</li>';
        return;
      }

      filtered.forEach(item => {
        const li = document.createElement('li');
        li.style.cssText = "background:#fdfdfd; padding:12px; border:1px solid #eee; border-radius:4px; margin-bottom:8px; list-style:none;";
        li.innerHTML = `
          <h4 style="margin: 0;"><a href="${item.url}" style="color: #0056b3; text-decoration: none;">${item.title}</a></h4>
          <small style="color: #888;">Tags: ${item.tags}</small>
        `;
        results.appendChild(li);
      });
    });
  })();
</script>
