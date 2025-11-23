---
layout: page
title: Projetos e Materiais
header: Projetos
permalink: /projects/
lang: pt-BR
nav_key: projects
nav_order: 4
---

Explore e conheça um pouco do meu trabalho a partir de amostras dos meus planos de aula, vídeo-aulas, materiais paradidáticos e projetos realizados - concebidos para ter os alunos no centro do processo de ensino-aprendizagem.

<div class="privacy-notice">
    <p><strong>Nota</strong>: Fotografias, ilustrações e amostras de trabalhos estudantis não estão incluídas neste portfólio. Esta é uma medida de respeito, segurança e proteção à privacidade dos alunos e alunas, em estrita observância aos princípios da <strong>Lei Geral de Proteção de Dados Pessoais (LGPD)</strong> e do <strong>Estatuto da Criança e do Adolescente (ECA)</strong>, garantindo a confidencialidade e o uso responsável de dados pessoais.</p>
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