---
layout: page
title: About Me
header: About
permalink: /about/
lang: en
nav_key: about
nav_order: 2
---
---
{% include translate.html %}
{% assign profile = site.data.cv.profile[page.lang] %}
{% assign education = site.data.cv.education | where: "lang", page.lang | sort: "start_date" | reverse %}

<!-- Atuais primeiro, depois por data -->
{% assign current_exp = site.data.cv.experience | where: "lang", page.lang | where: "current", true | sort: "start_date" | reverse %}
{% assign past_exp = site.data.cv.experience | where: "lang", page.lang | where: "current", false | sort: "start_date" | reverse %}
{% assign experience = current_exp | concat: past_exp %}

{% assign skill_categories = site.data.cv.skills.categories | where: "lang", page.lang %}

{% assign skill_categories = site.data.cv.skills.categories | where: "lang", page.lang %}

<div class="video-intro-section">
    <div class="video-container">
        <video controls poster="/assets/images/video-thumbnail.jpg">
            <source src="/assets/videos/curriculo-video.mp4" type="video/mp4">
            Seu navegador não suporta vídeos HTML5.
        </video>
    </div>
    <div class="video-description">
        <p>
            {{ t.about.intro_1 }}
        </p>
        <p>
            {{ t.about.intro_2 }}
        </p>
        <div class="cv-download">
            <a href="/assets/documents/Lucas_Liza_Professor_de_História.pdf" download class="btn-download">
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                    <polyline points="7 10 12 15 17 10"></polyline>
                    <line x1="12" y1="15" x2="12" y2="3"></line>
                </svg>
                {{ t.about.download_cv }}
            </a>
        </div>
    </div>
</div>

<div class="collapsible-sections">
    <div class="section-collapsible">
        <button class="section-toggle" data-section="education">
            <span class="section-title">
                {{ t.about.education_title }}
            </span>
            <span class="toggle-icon">▼</span>
        </button>
        <div class="section-content" id="education" style="display: block;">
            {% for edu in education %}
            <div class="timeline-item">
                <div class="item-title">{{ edu.degree }}</div>
                <div class="item-meta">
                    {{ edu.institution }} · 
                    {{ edu.start_date | date: "%Y" }} - 
                    {% if edu.end_date == "present" %}Presente{% else %}{{ edu.end_date | date: "%Y" }}{% endif %}
                </div>
                <div class="item-description">{{ edu.description }}</div>
            </div>
            {% endfor %}
        </div>
    </div>
    <div class="section-collapsible">
        <button class="section-toggle" data-section="experience">
            <span class="section-title">
                {{ t.about.experience_title }}
            </span>
            <span class="toggle-icon">▼</span>
        </button>
<div class="section-content" id="experience" style="display: block;">
            {% for exp in experience %}
            <div class="timeline-item">
                {% if exp.current %}
                <div class="item-badge current">Atual</div>
                {% endif %}
                <div class="item-title">{{ exp.title }}</div>
                <div class="item-meta">
                    {{ exp.organization }} · 
                    {{ exp.start_date | date: "%Y" }} - 
                    {% if exp.current %}Presente{% else %}{{ exp.end_date | date: "%Y" }}{% endif %}
                </div>
                <div class="item-description">{{ exp.description }}</div>
            </div>
            {% endfor %}
        </div>
    </div>
    <div class="section-collapsible">
        <button class="section-toggle" data-section="skills" >
            <span class="section-title">
                {{ t.about.competences_title }}
            </span>
            <span class="toggle-icon">▼</span>
        </button>
        <div class="section-content" id="skills">
            <div class="skills-categories">
                {% for category in skill_categories %}
                <div class="skill-category">
                    <h4>{{ category.icon }} {{ category.name }}</h4>
                    <div class="skill-tags">
                        {% for skill in category.skills %}
                        <span class="skill-tag" data-level="{{ skill.level }}">
                            {{ skill.name }}
                        </span>
                        {% endfor %}
                    </div>
                </div>
                {% endfor %}
            </div>
        </div>
    </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
    // Toggle sections
    const toggleButtons = document.querySelectorAll('.section-toggle');
    
    toggleButtons.forEach(button => {
        button.addEventListener('click', function() {
            const sectionId = this.getAttribute('data-section');
            const content = document.getElementById(sectionId);
            const parent = this.closest('.section-collapsible');
            
            // Toggle display
            if (content.style.display === 'none' || content.style.display === '') {
                content.style.display = 'block';
                parent.classList.remove('collapsed');
            } else {
                content.style.display = 'none';
                parent.classList.add('collapsed');
            }
        });
    });
});
</script>