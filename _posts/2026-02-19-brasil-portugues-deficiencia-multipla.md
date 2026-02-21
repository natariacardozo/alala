---
layout: default
---
<article class="post">
  <h1>{{ page.titulo_original }}</h1>
  
  <div class="post-metadata" style="background: #f9f9f9; padding: 15px; border-left: 5px solid #0056b3; margin-bottom: 20px;">
    <strong>Autores:</strong> {{ page.autores | join: ", " }} <br>
    <strong>Ano:</strong> {{ page.ano }} | <strong>Periódico:</strong> {{ page.periodico }} <br>
    <hr>
    <strong>📍 País:</strong> {{ page.pais | join: ", " }} <br>
    <strong>🗣️ Língua Avaliada:</strong> {{ page.lingua_avaliada | join: ", " }} <br>
    <strong>📂 Categorias:</strong> {{ page.categorias | join: ", " }}
  </div>

  <div class="post-content">
    <h3>Resumo Original</h3>
    <p>{{ page.resumo_original }}</p>
    
    <hr>
    {{ content }}
    <hr>
    
    <a href="{{ page.link }}" target="_blank" class="button">Acessar Documento Original</a>
  </div>
</article>
