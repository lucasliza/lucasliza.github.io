---
layout: page
title: Projetos & Materiais
header: Projetos
permalink: /projects/
lang: pt-BR
---

Conheça um pouco do meu trabalho a partir de amostras dos meus planos de aula, vídeo-aulas, materiais paradidáticos e projetos realizados - todos, é claro, concebidos para envolver os alunos em investigações históricas significativas.

<div class="privacy-notice">
    <p>Nota: Imagens e amostras de trabalhos estudantis não estão incluídas neste portfólio para proteger a privacidade dos alunos e respeitar a confidencialidade institucional.</p>
</div>

<div class="projects-list">
{% for project in site.projects %}
    <div class="project">
        <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
        <p>{{ project.excerpt }}</p>
        {% if project.tags %}
        <div class="tags">
            {% for tag in project.tags %}
            <span class="tag">{{ tag }}</span>
            {% endfor %}
        </div>
        {% endif %}
    </div>
{% endfor %}
</div>