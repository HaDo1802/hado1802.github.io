---
title: "Home"
---

{% assign experience_count = site.data.experience | size %}
{% assign project_count = site.data.projects | size %}

<section id="about" class="hero section enterprise-hero">
  <div class="hero-grid ide-hero-grid">
    <div class="hero-main ide-left">
      <div class="visitor-badge">
        <span class="pulse-dot" aria-hidden="true"></span>
        <span>1,767 unique visitors</span>
      </div>

      <h1>Hello <span aria-hidden="true">👋</span> <br>I&apos;m <span class="gradient-name">Ha Do</span></h1>

      <p class="typing-line">
        <span class="mono-text">1000+ SQL questions solved</span><span class="typing-cursor">|</span>
      </p>

      <p class="hero-copy">
        Data analyst, data engineer, and analytical engineer focused on reliable pipelines, scalable transformation layers,
        and business-facing analytics systems that teams can trust in production.
      </p>

      <div class="social-links hero-socials" aria-label="Social links">
        <a href="https://www.linkedin.com/in/ha-van-do/" target="_blank" rel="noopener" aria-label="LinkedIn">
          <i class="fa-brands fa-linkedin-in"></i>
        </a>
        <a href="https://github.com/HaDo1802" target="_blank" rel="noopener" aria-label="GitHub">
          <i class="fa-brands fa-github"></i>
        </a>
        <a href="https://leetcode.com" target="_blank" rel="noopener" aria-label="LeetCode">
          <i class="fa-solid fa-code"></i>
        </a>
        <a href="#certificates" aria-label="Certificates">
          <i class="fa-solid fa-circle-check"></i>
        </a>
        <a href="mailto:havando1802@gmail.com" aria-label="Email">
          <i class="fa-solid fa-envelope"></i>
        </a>
      </div>

      <div class="hero-actions">
        <a class="btn coffee-cta" href="mailto:havando1802@gmail.com?subject=Coffee%20Chat%20with%20Ha%20Do">Book a coffee chat (free)</a>
      </div>

      <ul class="hero-stats" aria-label="Portfolio summary">
        <li>
          <strong>{{ experience_count }}+</strong>
          <span>Industry Roles</span>
        </li>
        <li>
          <strong>{{ project_count }}+</strong>
          <span>Projects Shipped</span>
        </li>
        <li>
          <strong>10+</strong>
          <span>Core Data Tools</span>
        </li>
      </ul>
    </div>

    <aside class="hero-side ide-right" aria-label="Code editor style profile card">
      <div class="code-glow" aria-hidden="true"></div>
      <div class="code-editor-card">
        <div class="editor-dots" aria-hidden="true">
          <span class="dot red"></span>
          <span class="dot yellow"></span>
          <span class="dot green"></span>
        </div>

        <pre class="editor-code" aria-label="SQL snippet"><code><span class="sql-keyword">SELECT</span> <span class="sql-text">*</span>
<span class="sql-keyword">FROM</span> <span class="sql-table">ha_do_experience</span>
<span class="sql-keyword">WHERE</span> <span class="sql-column">role</span> = <span class="sql-value">'Data Engineer'</span>
<span class="sql-keyword">AND</span> <span class="sql-column">impact</span> = <span class="sql-value">'High'</span>;</code></pre>

        <div class="editor-bars" aria-hidden="true">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>
      <div class="blueprint-grid" aria-hidden="true"></div>
      <img src="{{ '/assets/images/me.jpeg' | relative_url }}" alt="Portrait of Ha Do" class="profile-pic ide-profile-pic">
    </aside>
  </div>
</section>

<section class="section capabilities" aria-label="Core capabilities">
  <div class="section-header">
    <h2>What I Build</h2>
  </div>
  <div class="cap-grid">
    <article class="cap-card">
      <h3>Reliable Data Pipelines</h3>
      <p>Automated extraction, transformation, and orchestration pipelines with reproducible runs and clean failure handling.</p>
    </article>
    <article class="cap-card">
      <h3>Analytics-Ready Models</h3>
      <p>Dimensional marts and dbt-friendly transformations that accelerate dashboarding and deep analytical queries.</p>
    </article>
    <article class="cap-card">
      <h3>Decision Systems</h3>
      <p>Forecasting, pricing, and optimization workflows that help stakeholders move faster with evidence-backed decisions.</p>
    </article>
  </div>
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

<section id="projects" class="section">
  <div class="section-header">
    <h2>Featured Projects</h2>
    <a class="view-all" href="https://github.com/{{ site.github_username }}" target="_blank" rel="noopener">All repositories</a>
  </div>
  <div class="projects-grid">
    {% for item in site.data.projects %}
    <article class="card project-card">
      <a class="thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open {{ item.title }}">
        <img src="{{ item.image | default: '/assets/images/placeholder_project.jpg' | relative_url }}"
             alt="{{ item.title | escape }} thumbnail"
             loading="lazy"
             {% if item.preview_gif %}data-preview="{{ item.preview_gif | relative_url }}"{% endif %}>
      </a>
      <div class="card-body">
        <h3 class="card-title"><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
        <p class="card-text">{{ item.description }}</p>
        {% if item.stack %}<p class="card-tags">{{ item.stack }}</p>{% endif %}
        {% if item.skills_icons %}
        <div class="project-skills" aria-label="Project skill icons">
          {% for skill in item.skills_icons %}
          <img src="{{ skill.src | relative_url }}" alt="{{ skill.alt | escape }} icon" loading="lazy" class="project-skill-icon">
          {% endfor %}
        </div>
        {% endif %}
        <div class="card-actions">
          {% if item.screenshot %}<a href="#" class="btn ghost" data-lightbox-src="{{ item.screenshot | relative_url }}">Preview</a>{% endif %}
          <a class="btn" href="{{ item.link }}" target="_blank" rel="noopener">Open Project</a>
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
      <a class="btn" href="mailto:havando1802@gmail.com?subject=Coffee%20Chat%20with%20Ha%20Do&body=Hi%20Ha%2C%0A%0AI%20would%20love%20to%20schedule%20a%20coffee%20chat.%20Here%20are%20a%20few%20times%20that%20work%20for%20me%3A%0A-%20%0A-%20%0A%0AThanks!">Schedule by Email</a>
      <a class="btn ghost" href="https://github.com/HaDo1802" target="_blank" rel="noopener">View GitHub</a>
    </div>
  </div>
</section>
