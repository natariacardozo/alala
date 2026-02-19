---
layout: default
title: Home
is_home: true
---

> O ALALA é um esforço de curadoria para que as avaliações de línguas na América Latina não sejam apenas dados, mas rastros de cultura e identidade.

---

### 🌎 Navegação por Eixos
Utilize os atalhos abaixo para explorar o acervo por categorias específicas:

| **Por Território** | **Por Idioma** | **Por Categoria** |
| :--- | :--- | :--- |
| [Mapeamento Chile]({{ '/tag.html?tag=chile' | relative_url }}) | [Língua Espanhola]({{ '/tag.html?tag=espanhol' | relative_url }}) | [Instrumentos DEA]({{ '/tag.html?tag=dea' | relative_url }}) |
| [Mapeamento Colômbia]({{ '/tag.html?tag=colombia' | relative_url }}) | [Língua Portuguesa]({{ '/tag.html?tag=portugues' | relative_url }}) | [Formação (LAL)]({{ '/tag.html?tag=lal' | relative_url }}) |
| [Mapeamento Brasil]({{ '/tag.html?tag=brasil' | relative_url }}) | [Língua Inglesa]({{ '/tag.html?tag=ingles' | relative_url }}) | [Acessibilidade]({{ '/tag.html?tag=acessibilidade' | relative_url }}) |

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
