---
layout: default
title: "ALALA - Início"
---

Em defesa da identidade, da ética e da soberania científica latino-americana.

---

<style>
  /* Estilo acadêmico e limpo */
  body { font-size: 14px; line-height: 1.6; color: #333; }
  h2 { font-size: 1.3em !important; border-bottom: 1px solid #eee; padding-bottom: 5px; margin-top: 25px; }
  h4 { font-size: 1.1em !important; margin-bottom: 2px; color: #0056b3; }
  .tag-container { font-size: 12px; color: #666; margin-bottom: 10px; }
  
 <input type="text" id="search-input" placeholder="Pesquisar por título, país, tag ou autor..." 
       style="width: 100%; padding: 12px; font-size: 16px; border: 2px solid #0056b3; border-radius: 6px; outline: none;">
<ul id="results-container" style="list-style: none; padding: 0; margin-top: 10px;"></ul>

<script>
  (function() {
    let searchData = [];
    const searchInput = document.getElementById('search-input');
    const resultsContainer = document.getElementById('results-container');

    // Carrega os dados assim que a página abre
    fetch('{{ "/search.json" | relative_url }}')
      .then(response => response.json())
      .then(data => {
        searchData = data;
      })
      .catch(err => console.error("Erro ao carregar o índice de busca:", err));

    // Escuta cada tecla digitada (Tempo Real)
    searchInput.addEventListener('input', function() {
      const query = this.value.toLowerCase().trim();
      resultsContainer.innerHTML = '';

      if (query.length < 2) return; // Só busca com 2 ou mais letras

      const filtered = searchData.filter(item => 
        item.title.toLowerCase().includes(query) || 
        item.tags.toLowerCase().includes(query) ||
        item.resumo.toLowerCase().includes(query)
      );

      filtered.forEach(item => {
        const li = document.createElement('li');
        li.style.cssText = "background: #f9f9f9; padding: 10px; border-bottom: 1px solid #ddd; margin-bottom: 5px;";
        li.innerHTML = `
          <h4 style="margin: 0;"><a href="${item.url}" style="color: #0056b3; text-decoration: none;">${item.title}</a></h4>
          <small style="color: #666;">Tags: ${item.tags}</small>
        `;
        resultsContainer.appendChild(li);
      });
    });
  })();
</script>

| **Por Território** | **Por Idioma** | **Por Categoria** |
| :--- | :--- | :--- |
| [Chile](/pais/chile) | [Espanhol](/idioma/espanhol) | [Instrumentos DEA](/categoria/dea) |
| [Colômbia](/pais/colombia) | [Português](/idioma/portugues) | [Formação (LAL)](/categoria/lal) |
| [Brasil](/pais/brasil) | [Inglês](/idioma/ingles) | [Acessibilidade](/categoria/acessibilidade) |

---

## 🆕 Adições Recentes ao Acervo
*Confira os últimos registros mapeados:*

{% for post in site.posts limit:5 %}
#### [{{
