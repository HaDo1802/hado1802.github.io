---
title: "Home"
---

{% assign project_count = site.data.projects | size %}
{% assign data_pipeline_count = site.data.projects | where: "category", "data-pipeline" | size %}
{% assign ml_statistics_count = site.data.projects | where: "category", "ml-statistics" | size %}
{% assign bi_dashboard_count = 0 %}
{% for p in site.data.projects %}
  {% if p.category == "bi-dashboard" %}
    {% assign bi_dashboard_count = bi_dashboard_count | plus: 1 %}
  {% elsif p.filter_categories %}
    {% if p.filter_categories contains "bi-dashboard" %}
      {% assign bi_dashboard_count = bi_dashboard_count | plus: 1 %}
    {% endif %}
  {% endif %}
{% endfor %}

<section id="about" class="hero section enterprise-hero">
  <div class="hero-grid ide-hero-grid">
    <div class="hero-main ide-left">
      <h1>
        I am <span class="gradient-name">Ha Do</span>
        <img class="name-accent-gif" src="https://user-images.githubusercontent.com/74038190/235294015-47144047-25ab-417c-af1b-6746820a20ff.gif" alt="" aria-hidden="true">
      </h1>

      <p class="hero-copy">
        Data Analytics Engineer @ Allegiant Air<br>
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
<span class="sql-keyword">WHERE</span> <span class="sql-column">role</span> = <span class="sql-value">'Data Analytics Engineer'</span>
<span class="sql-keyword">AND</span> <span class="sql-column">side interest</span> = <span class="sql-value">'Rhino Lover'</span>
<span class="sql-keyword">AND</span> <span class="sql-column">sport favourite</span> = <span class="sql-value">'Soccer Fan'</span>
<span class="sql-keyword">AND</span> <span class="sql-column">personality</span> = <span class="sql-value">'Passionate'</span>;</code></pre>

        <div class="editor-bars" aria-hidden="true">
          <span></span>
          <span></span>
          <span></span>
        </div>
      </div>

      <div class="social-links hero-socials" aria-label="Social links">
        <a href="mailto:havando1802@gmail.com" aria-label="Email">
          <i class="fa-solid fa-envelope"></i>
        </a>
        <a href="tel:+16823748218" aria-label="Phone">
          <i class="fa-solid fa-phone"></i>
        </a>
        <a href="https://www.linkedin.com/in/ha-van-do/" target="_blank" rel="noopener" aria-label="LinkedIn">
          <i class="fa-brands fa-linkedin-in"></i>
        </a>
        <a href="https://github.com/HaDo1802" target="_blank" rel="noopener" aria-label="GitHub">
          <i class="fa-brands fa-github"></i>
        </a>
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

<section id="experience" class="section experience-section" aria-labelledby="experience-heading">
  <div class="section-header experience-section__header">
    <h2 id="experience-heading">Experience</h2>
  </div>

  <div class="exp-visual" role="list">
    <div class="exp-visual__rail" aria-hidden="true"></div>
    {% for item in site.data.experience %}
    <article
      class="exp-visual__row js-exp-reveal"
      role="listitem"
      style="--exp-i: {{ forloop.index0 }}"
    >
      <span class="sr-only">{{ item.position }} at {{ item.company }}, {{ item.start_date }} — {{ item.end_date }}</span>
      <div class="exp-visual__meta">
        <div class="exp-visual__dates">
          <span class="exp-visual__date-start">{{ item.start_date }}</span>
          <span class="exp-visual__date-sep" aria-hidden="true">—</span>
          <span class="exp-visual__date-end">{{ item.end_date }}</span>
        </div>
        <div class="exp-visual__axis">
          <span class="exp-visual__node"></span>
          <span class="exp-visual__connector" aria-hidden="true"></span>
        </div>
      </div>
      <div class="exp-visual__card">
        {% if item.company_link %}
        <a class="exp-visual__media" href="{{ item.company_link }}" target="_blank" rel="noopener" tabindex="-1" aria-hidden="true">
        {% else %}
        <div class="exp-visual__media exp-visual__media--static">
        {% endif %}
          <div class="exp-visual__media-inner">
            {% if item.image %}
            <img
              class="exp-visual__img"
              src="{{ item.image | relative_url }}"
              alt=""
              width="800"
              height="520"
              loading="lazy"
              decoding="async"
            >
            {% endif %}
            <div class="exp-visual__media-gradient" aria-hidden="true"></div>
          </div>
        {% if item.company_link %}
        </a>
        {% else %}
        </div>
        {% endif %}
        <div class="exp-visual__panel">
          <div class="exp-visual__panel-content">
            <h3 class="exp-visual__role">{{ item.position }}</h3>
            {% if item.company_link %}
            <a class="exp-visual__company" href="{{ item.company_link }}" target="_blank" rel="noopener">{{ item.company }}</a>
            {% else %}
            <span class="exp-visual__company exp-visual__company--text">{{ item.company }}</span>
            {% endif %}
            {% if item.team %}
            <p class="exp-visual__team">{{ item.team }}</p>
            {% endif %}
            <p class="exp-visual__location">
              <i class="fa-solid fa-location-dot" aria-hidden="true"></i>
              <span>{{ item.location }}</span>
            </p>
          </div>
        </div>
      </div>
    </article>
    {% endfor %}
  </div>
</section>

<section id="projects" class="section works-section" aria-label="Featured project">
  <div class="section-header works-header">
    <h2>Featured Project</h2>
  </div>

  <div class="works-filters" role="tablist" aria-label="Project filters">
    <button class="works-filter-btn is-active" type="button" data-filter-btn data-filter="all">All ({{ project_count }})</button>
    <button class="works-filter-btn" type="button" data-filter-btn data-filter="data-pipeline">Data Pipeline ({{ data_pipeline_count }})</button>
    <button class="works-filter-btn" type="button" data-filter-btn data-filter="ml-statistics">ML &amp; Statistics ({{ ml_statistics_count }})</button>
    <button class="works-filter-btn" type="button" data-filter-btn data-filter="bi-dashboard">BI &amp; Dashboards ({{ bi_dashboard_count }})</button>
  </div>

  <div class="works-grid">
    {% for item in site.data.projects %}
    <article class="works-card" data-work-card data-category="{% if item.filter_categories %}{{ item.filter_categories | join: ' ' }}{% else %}{{ item.category }}{% endif %}">
      <div class="works-media">
        <a class="works-thumb" href="{{ item.link }}" target="_blank" rel="noopener" aria-label="Open {{ item.title }}">
          <img
            src="{{ item.media.cover | default: '/assets/images/placeholder_project.jpg' | relative_url }}"
            {% if item.media.preview %}data-preview="{{ item.media.preview | relative_url }}"{% endif %}
            alt="{{ item.title | escape }} thumbnail"
            loading="lazy"
          >
          <span class="works-thumb-overlay" aria-hidden="true"></span>
          <span class="works-tag">{{ item.category_label }}</span>
        </a>
        {% if item.media.screenshot %}
        <button class="works-expand-btn" type="button" data-lightbox-src="{{ item.media.screenshot | relative_url }}" aria-label="Preview {{ item.title }}">
          <i class="fa-solid fa-up-right-and-down-left-from-center" aria-hidden="true"></i>
        </button>
        {% endif %}
      </div>
      <div class="works-body">
        <div class="works-kicker">{{ item.category_label }}</div>
        <h3><a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a></h3>
        <p>{{ item.description }}</p>
        {% if item.skills_icons %}
        <div class="works-tools" aria-label="Project tools">
          <div class="works-tools-label">Tech Stack</div>
          <ul class="works-tools-list" aria-label="Tech stack">
          {% for skill in item.skills_icons %}
          <li class="works-tool" title="{{ skill.alt }}" aria-label="{{ skill.alt }}">
            <span class="works-tool-icon" aria-hidden="true">
              {% if skill.src %}<img src="{{ skill.src | relative_url }}" alt="" loading="lazy">{% elsif skill.icon %}<i class="{{ skill.icon }}"></i>{% else %}<span class="works-tool-fallback">{{ skill.alt | slice: 0, 1 }}</span>{% endif %}
            </span>
            <span class="sr-only">{{ skill.alt }}</span>
          </li>
          {% endfor %}
          </ul>
        </div>
        {% elsif item.stack %}
        <div class="works-tools" aria-label="Project tools">
          <div class="works-tools-label">Tech Stack</div>
          <div class="works-tools-list">
            <span class="works-tool works-tool--stack" aria-label="{{ item.stack }}">
              <span class="works-tool-icon" aria-hidden="true"><i class="fa-solid fa-microchip"></i></span>
              <span class="works-tool-stack-copy">{{ item.stack }}</span>
            </span>
          </div>
        </div>
        {% endif %}
        <div class="works-footer">
          <a class="works-link" href="{{ item.link }}" target="_blank" rel="noopener">
            View Project
            <i class="fa-solid fa-arrow-up-right-from-square" aria-hidden="true"></i>
          </a>
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
        I enjoy working on data engineering pipelines, analytics automation, and MLOps design.
        If you are hiring or collaborating, I would be glad to connect.
      </p>
      <div class="contact-meta" aria-label="Direct contact details">
        <a class="contact-meta__item" href="mailto:havando1802@gmail.com">
          <i class="fa-solid fa-envelope"></i>
          <span>havando1802@gmail.com</span>
        </a>
        <a class="contact-meta__item" href="tel:+16823748218">
          <i class="fa-solid fa-phone"></i>
          <span>(682) 374-8218</span>
        </a>
      </div>
      <div class="contact-actions">
        <a class="btn" href="mailto:havando1802@gmail.com">Email Me</a>
        <a class="btn ghost" href="tel:+16823748218">Call Me</a>
        <a class="btn ghost" href="https://www.linkedin.com/in/ha-van-do/" target="_blank" rel="noopener">Message on LinkedIn</a>
      </div>
    </div>
  </div>
</section>
