---
layout: default
title: Home
lang: en
permalink: /
nav_key: home
nav_order: 1
---
<div class="hero">
    <div class="hero-grid">
        <div class="hero-image">
            <img src="{{ '/assets/images/profile-2.jpg' | relative_url }}" alt="{{ site.author }}">
        </div>
        <div class="hero-text">
            <h1>{{ site.author }}</h1>
            <p class="hero-subtitle">{{ site.data.translations.home.subtitle[page.lang] }}</p>
            <p class="hero-description">
                {{ site.data.translations.home.description_1[page.lang] }}
            </p>
            <p class="hero-description">
                {{ site.data.translations.home.description_2[page.lang] }}
            </p>
            <div class="hero-buttons">
                <a href="{{ '/about/' | relative_url }}" class="btn-primary">{{ site.data.translations.home.btn_learn_more[page.lang] }}</a>
                <a href="{{ '/contact/' | relative_url }}" class="btn-secondary">{{ site.data.translations.home.btn_contact[page.lang] }}</a>
            </div>
        </div>
    </div>
</div>

<section class="home-intro">
    <div class="container">
        <h2>{{ site.data.translations.home.welcome_title[page.lang] }}</h2>
        <p class="intro-large">
            {{ site.data.translations.home.welcome_text[page.lang] }}
        </p>
    </div>
</section>