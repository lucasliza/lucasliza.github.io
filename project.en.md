---
layout: page
title: Projects & Resources
permalink: /projects/
lang: en
---

A collection of lesson plans, curriculum materials, and innovative projects designed to engage students in meaningful historical inquiry.

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