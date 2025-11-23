---
layout: default
title: Página de Inicio
lang: es
permalink: /
nav_key: home
nav_order: 1
---
{% include translate.html %}
<div class="hero">
    <div class="hero-grid">
        <div class="hero-image">
            <img src="{{ '/assets/images/profile-2.jpg' | relative_url }}" alt="{{ site.author }}">
        </div>
        <div class="hero-text">
            <h1>{{ site.author }}</h1>
            <p class="hero-subtitle">{{ t.home.subtitle }}</p>
            <p class="hero-description">
                {{ t.home.description_1 }}
            </p>
            <p class="hero-description">
                {{ t.home.description_2 }}
            </p>
            <div class="hero-buttons">
                <a href="{{ '/about/' | relative_url }}" class="btn-primary">{{ t.home.btn_learn_more}}</a>
                <a href="{{ '/contact/' | relative_url }}" class="btn-secondary">{{ t.home.btn_contact}}</a>
            </div>
        </div>
    </div>
</div>

<section class="home-intro">
    <div class="container">
        <h2>{{ t.home.welcome_title }}</h2>
        <p class="intro-large">
            {{ t.home.welcome_text }}
        </p>
    </div>
</section>