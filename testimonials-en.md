---
layout: page
title: Testimonials and recommendations
header: Testimonials
permalink: /testimonials/
lang: en
nav_key: testimonials
nav_order: 5
---
{% include translate.html %}
<div class="testimonials-intro">
    <p class="intro-text">
        {{ t.testimonials.intro }}
    </p>

    <div class="authenticity-note">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M9 12l2 2 4-4"></path>
            <circle cx="12" cy="12" r="10"></circle>
        </svg>
        <span>{{ t.testimonials.authenticity_note }}</span>
    </div>
</div>

<div class="testimonials-grid">
    {% assign testimonials = site.testimonials | where: "lang", page.lang | sort: "date" | reverse %}
    
    {% for testimonial in testimonials %}
    <article class="testimonial-card {% if testimonial.featured %}featured{% endif %}">
        
        {% if testimonial.featured %}
        <div class="featured-badge">{{ t.testimonials.featured_badge }}</div>
        {% endif %}
        
        <div class="testimonial-header">
            <div class="testimonial-author">
                <h3>{{ testimonial.author_name }}</h3>
                <p class="author-role">{{ testimonial.author_role }}</p>
                <p class="author-institution">{{ testimonial.author_institution }}</p>
                <p class="author-period">{{ testimonial.period }}</p>
            </div>
        </div>
        
        <div class="testimonial-content">
            <blockquote>
                {{ testimonial.content }}
            </blockquote>
        </div>
        
        <div class="testimonial-footer">
            <a href="{{ testimonial.pdf_url }}" 
               class="pdf-link" 
               download>
                <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path>
                    <polyline points="14 2 14 8 20 8"></polyline>
                    <line x1="16" y1="13" x2="8" y2="13"></line>
                    <line x1="16" y1="17" x2="8" y2="17"></line>
                </svg>
                {{ t.testimonials.pdf_link_text }}
            </a>
            <span class="testimonial-date">
                {{ t.testimonials.written_on }} 
                {{ testimonial.date | date: "%Y" }}
            </span>
        </div>
    </article>
    {% endfor %}
</div>

<div class="testimonials-cta">
    <div class="cta-content">
        <h2>{{ t.testimonials.cta_title }}</h2>
        <p>{{ t.testimonials.cta_description }}</p>
        <div class="cta-buttons">
            <a href="/contato/" class="btn-primary">
                {{ t.home.btn_contact }}
            </a>
            <a href="/assets/documents/Lucas_Liza_Professor_de_Historia.pdf" class="btn-secondary" download>
                {{ t.about.download_cv }}
            </a>
        </div>
    </div>
</div>

<div class="verification-notice">
    <h3>{{ t.testimonials.verification_title }}</h3>
    <p>{{ t.testimonials.verification_text }}</p>
</div>