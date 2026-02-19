---
layout: default
title: Home
---

> "A avaliação não é apenas um instrumento técnico; é uma prática social que reflete identidades e territórios."

---

### 🌎 Navegação por Eixos
Utilize os atalhos abaixo para explorar o acervo por categorias específicas:

| **Por Território** | **Por Idioma** | **Por Categoria** |
| :--- | :--- | :--- |
| [Mapeamento Chile]({{ '/tag/chile' | relative_url }}) | [Língua Espanhola]({{ '/tag/espanhol' | relative_url }}) | [Instrumentos DEA]({{ '/tag/dea' | relative_url }}) |
| [Mapeamento Colômbia]({{ '/tag/colombia' | relative_url }}) | [Língua Portuguesa]({{ '/tag/portugues' | relative_url }}) | [Formação (LAL)]({{ '/tag/lal' | relative_url }}) |
| [Mapeamento Brasil]({{ '/tag/brasil' | relative_url }}) | [Língua Inglesa]({{ '/tag/ingles' | relative_url }}) | [Acessibilidade]({{ '/tag/acessibilidade' | relative_url }}) |

---

### 🆕 Adições Recentes ao Acervo
*Confira os últimos registros mapeados na nossa base de dados:*

<div class="ultimos-posts">
  {% for post in site.posts limit:5 %}
    <article style="margin-bottom: 20px;">
      <h4 style="margin-bottom: 5px;">
        <a href="{{ post.url | relative_url }}" style="color: #1A365D; text-decoration: none;">
          {{ post.title }}
        </a>
      </h4>
      <small><strong>Tags:</strong> {{ post.tags | join: ", " }}</small><br>
      <p style="font-size: 0.9em; margin-top: 5px;">{{ post.summary }}</p>
    </article>
  {% endfor %}
</div>

<br>

---
