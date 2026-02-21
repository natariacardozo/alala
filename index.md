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
  
  /* Barra de Pesquisa */
  #search-input {
    width: 100%;
    padding: 12px;
    font-size: 15px;
    border: 2px solid #0056b3;
    border-radius: 6px;
    margin-bottom: 10px;
    outline: none;
  }
  #results-container { 
    list-style: none; 
    padding: 0; 
    margin-bottom: 30px; 
    border-radius: 4px;
  }
  #results-container li { 
    background: #fdfdfd; 
    padding: 12px; 
    border: 1px solid #eee; 
    border-top: none; 
  }
  #results-container li:first-child { border-top: 1px solid #eee; }
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
#### [{{
