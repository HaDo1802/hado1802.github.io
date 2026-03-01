---
title: "Home"
---

{% assign experience_count = site.data.experience | size %}
{% assign project_count = site.data.projects | size %}

<section id="about" class="hero section enterprise-hero">
  <div class="hero-grid ide-hero-grid">
    <div class="hero-main ide-left">
      <h1>I am <span class="gradient-name">Ha Do</span></h1>

      <p class="hero-copy">
        Data Analyst @ Allegiant Air<br>
        TCU Class of 2025
      </p>

      <div class="code-editor-card hero-code-card">
        <div class="editor-dots" aria-hidden="true">
          <span class="dot red"></span>
          <span class="dot yellow"></span>
          <span class="dot green"></span>
        </div>

        <pre class="editor-code" aria-label="SQL snippet"><code><span class="sql-keyword">SELECT</span> <span class="sql-text">*</span>
<span class="sql-keyword">FROM</span> <span class="sql-table">ha_do_experience</span>
<span class="sql-keyword">WHERE</span> <span class="sql-column">role</span> = <span class="sql-value">'Data Analyst'</span>
<span class="sql-keyword">AND</span> <span class="sql-column">role</span> = <span class="sql-value">'Rhino Lover'</span>
<span class="sql-keyword">AND</span> <span class="sql-column">role</span> = <span class="sql-value">'Soccer Fan'</span>
<span class="sql-keyword">AND</span> <span class="sql-column">impact</span> = <span class="sql-value">'High'</span>;</code></pre>

        <div class="editor-bars" aria-hidden="true">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>

      <div class="social-links hero-socials" aria-label="Social links">
        <a href="https://www.linkedin.com/in/ha-van-do/" target="_blank" rel="noopener" aria-label="LinkedIn">
          <i class="fa-brands fa-linkedin-in"></i>
        </a>
        <a href="https://github.com/HaDo1802" target="_blank" rel="noopener" aria-label="GitHub">
          <i class="fa-brands fa-github"></i>
        </a>
        <a href="mailto:havando1802@gmail.com" aria-label="Email">
          <i class="fa-solid fa-envelope"></i>
        </a>
      </div>

      <div class="hero-actions">
        <a class="btn coffee-cta" href="{{ site.coffee_chat_url }}" target="_blank" rel="noopener">Book a coffee chat (free)</a>
      </div>

    </div>

    <aside class="hero-side ide-right" aria-label="Code editor style profile card">
      <figure class="profile-figure">
        <img src="{{ '/assets/images/me.jpeg' | relative_url }}" alt="Portrait of Ha Do" class="profile-pic ide-profile-pic">
        <figcaption class="profile-note">Trying to learn golf ⛳. Scorecard says one thing, my confidence says another 😅</figcaption>
      </figure>
    </aside>
  </div>
</section>

<section class="quote-section section" aria-label="Personal quote">
  <p class="quote-text">"The goal is not to read a book, the goal is to become a reader."</p>
  <p class="quote-author">James Clear</p>
</section>

<section id="experience" class="section">
  <div class="section-header">
    <h2>Experience Timeline</h2>
  </div>
  <div class="experience-list">
    {% for item in site.data.experience %}
    <article class="experience-card">
      <div class="experience-core">
        <p class="experience-dates">{{ item.start_date }} — {{ item.end_date }}</p>
        <h3 class="experience-company">{{ item.company }}</h3>
        <p class="experience-position">{{ item.position }} · {{ item.location }}</p>
        <p class="experience-description">{{ item.description }}</p>
        {% if item.skills %}
        <div class="experience-skills">
          {% for skill in item.skills %}
          <span class="pill">{{ skill }}</span>
          {% endfor %}
        </div>
        {% endif %}
      </div>
      {% if item.image %}
      <a class="experience-media" href="{{ item.company_link | default: '#' }}" {% if item.company_link %}target="_blank" rel="noopener"{% endif %} aria-label="{{ item.company }} website">
        <img src="{{ item.image | relative_url }}" alt="{{ item.company }} logo or office">
      </a>
      {% endif %}
    </article>
    {% endfor %}
  </div>
</section>

<section id="projects" class="section works-section" aria-label="Featured project">
  <div class="section-header works-header">
    <h2>Featured Project</h2>
  </div>

  <div class="works-filters" role="tablist" aria-label="Project filters">
    <button class="works-filter-btn is-active" type="button" data-filter-btn data-filter="all">All (6)</button>
    <button class="works-filter-btn" type="button" data-filter-btn data-filter="data-pipeline">Data Pipeline (3)</button>
    <button class="works-filter-btn" type="button" data-filter-btn data-filter="ml-statistics">ML &amp; Statistics (2)</button>
    <button class="works-filter-btn" type="button" data-filter-btn data-filter="bi-dashboard">BI &amp; Dashboards (1)</button>
  </div>

  <div class="works-grid">
    {% for item in site.data.projects %}
    {% assign category = 'bi-dashboard' %}
    {% assign category_label = 'BI & Dashboards' %}
    {% if item.title contains 'Zillow Real Estate Analytics Pipelines' or item.title contains 'E-commerce Revenue Analysis' or item.title contains 'Zillow Data Extraction & Ingestion Pipeline' %}
      {% assign category = 'data-pipeline' %}
      {% assign category_label = 'Data Pipeline' %}
    {% elsif item.title contains 'Housing Price Prediction' or item.title contains 'Portfolio Optimization & Management' %}
      {% assign category = 'ml-statistics' %}
      {% assign category_label = 'ML & Statistics' %}
    {% endif %}
    <article class="works-card" data-work-card data-category="{{ category }}">
      <a class="works-thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open {{ item.title }}">
        <img src="{{ item.image | default: '/assets/images/placeholder_project.jpg' | relative_url }}" alt="{{ item.title | escape }} thumbnail" loading="lazy">
        <span class="works-tag">{{ category_label }}</span>
      </a>
      <div class="works-body">
        <h3><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
        <p>{{ item.description }}</p>
        {% if item.skills_icons %}
        <div class="works-tools" aria-label="Project tools">
          {% for skill in item.skills_icons %}
          <span><i class="fa-solid fa-microchip"></i>{{ skill.alt }}</span>
          {% endfor %}
        </div>
        {% elsif item.stack %}
        <div class="works-tools" aria-label="Project tools">
          <span><i class="fa-solid fa-microchip"></i>{{ item.stack }}</span>
        </div>
        {% endif %}
        <div class="card-actions">
          <a class="btn ghost" href="{{ item.link }}" target="_blank" rel="noopener">Open Project</a>
        </div>
      </div>
    </article>
    {% endfor %}
  </div>
</section>

<section id="certificates" class="section">
  <div class="section-header">
    <h2>Certificates</h2>
  </div>
  {% assign sql_pdf = '/assets/images/certificate/sql_advanced certificate.pdf' | relative_url | uri_escape %}
  {% assign mlops_pdf = '/assets/images/certificate/coursera_pythonessential_mlops.pdf' | relative_url %}
  <div class="cert-grid">
    <article class="cert-card">
      <a class="cert-preview" href="{{ sql_pdf }}" target="_blank" rel="noopener" aria-label="Open SQL Advanced certificate PDF">
        <iframe src="{{ sql_pdf }}#page=1&view=FitH" title="SQL Advanced Certificate preview"></iframe>
      </a>
      <div class="cert-icon"><i class="fa-solid fa-certificate"></i></div>
      <div>
        <h3>SQL Advanced Certificate</h3>
        <p>Advanced SQL querying, optimization, and analytical problem solving for business use cases.</p>
      </div>
      <a class="btn ghost" href="{{ sql_pdf }}" target="_blank" rel="noopener">View PDF</a>
    </article>
    <article class="cert-card">
      <a class="cert-preview" href="{{ mlops_pdf }}" target="_blank" rel="noopener" aria-label="Open Python Essentials for MLOps certificate PDF">
        <iframe src="{{ mlops_pdf }}#page=1&view=FitH" title="Python Essentials for MLOps Certificate preview"></iframe>
      </a>
      <div class="cert-icon"><i class="fa-solid fa-graduation-cap"></i></div>
      <div>
        <h3>Python Essentials for MLOps</h3>
        <p>Foundations for production-ready ML workflows, code quality practices, and operational reliability.</p>
      </div>
      <a class="btn ghost" href="{{ mlops_pdf }}" target="_blank" rel="noopener">View PDF</a>
    </article>
  </div>
</section>

<section id="contact" class="section contact-section">
  <div class="section-header">
    <h2>Let’s Build Something Useful</h2>
  </div>
  <div class="contact-layout">
    <div class="contact-panel">
      <h3>Collaborations and opportunities</h3>
      <p>
        I enjoy working on data engineering pipelines, analytics automation, and experiment-driven decision systems.
        If you are hiring or collaborating, I would be glad to connect.
      </p>
      <div class="contact-actions">
        <a class="btn" href="mailto:havando1802@gmail.com">Email Me</a>
        <a class="btn ghost" href="https://www.linkedin.com/in/ha-van-do/" target="_blank" rel="noopener">Message on LinkedIn</a>
      </div>
    </div>
    <div class="contact-panel coffee-panel">
      <h3>Schedule a Coffee Chat</h3>
      <p>Share a few possible times and I will confirm one with you.</p>
      <a class="btn" href="{{ site.coffee_chat_url }}" target="_blank" rel="noopener">Book on Calendly</a>
      <a class="btn ghost" href="https://github.com/HaDo1802" target="_blank" rel="noopener">View GitHub</a>
    </div>
  </div>
</section>
